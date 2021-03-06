---
title: Azure Site Recovery の 2 つの Azure リージョン間で仮想ネットワークをマッピングする | Microsoft Docs
description: Azure Site Recovery は、仮想マシンと物理サーバーのレプリケーション、フェールオーバー、回復を調整します。 Azure またはセカンダリ データセンターへのフェールオーバーについて説明します。
author: mayurigupta13
manager: rochakm
ms.service: site-recovery
ms.topic: conceptual
ms.date: 11/27/2018
ms.author: mayg
ms.openlocfilehash: fccc7379794b4b75ff53e517eddd95ff0f7db0e9
ms.sourcegitcommit: 95822822bfe8da01ffb061fe229fbcc3ef7c2c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "55223784"
---
# <a name="set-up-network-mapping-and-ip-addressing-for-vnets"></a>VNet のネットワーク マッピングと IP アドレス指定を設定する

この記事では、異なる Azure リージョンに配置されている Azure Virtual Network (VNet) のインスタンスをマッピングする方法と、ネットワーク間の IP アドレス指定を設定する方法について説明します。 ネットワーク マッピングを行うと、レプリケートされた VM はターゲットの Azure リージョンに作成されるだけでなく、ソース VM の VNet にマッピングされている VNet にも作成されます。

## <a name="prerequisites"></a>前提条件

ネットワークをマップする前に、[Azure VNet](../virtual-network/virtual-networks-overview.md) がソースとターゲットの Azure リージョンになければなりません。 

## <a name="set-up-network-mapping"></a>ネットワーク マッピングを設定する

次のようにネットワークをマップします。

1. **[Site Recovery インフラストラクチャ]** で、**[+ネットワーク マッピング]** をクリックします。

    ![ ネットワーク マッピングを作成します](./media/site-recovery-network-mapping-azure-to-azure/network-mapping1.png)

3. **[ネットワーク マッピングの追加]** で、ソースとターゲットの場所を選択します。 この例では、ソース VM は東アジア リージョンで実行されていて、東南アジア リージョンにレプリケートされます。

    ![ソースとターゲットを選択します ](./media/site-recovery-network-mapping-azure-to-azure/network-mapping2.png)
3. 次に、逆方向のネットワーク マッピングを作成します。 この例では、ソースが東南アジアになり、ターゲットが東アジアとなります。

    ![[ネットワーク マッピングの追加] ウィンドウ - ターゲット ネットワークのソースとターゲットの場所を選択する](./media/site-recovery-network-mapping-azure-to-azure/network-mapping3.png)


## <a name="map-networks-when-you-enable-replication"></a>レプリケーションを有効にするときにネットワークをマップする

Azure VM のディザスター リカバリーを構成する前にネットワーク マッピングを準備しておかなかった場合は、[レプリケーションをセットアップし、有効にする](azure-to-azure-how-to-enable-replication.md)ときにターゲット ネットワークを指定できます。 その場合は次のようになります。

- 選択したターゲットに基づいて、Site Recovery では、ソース リージョンからターゲット リージョンへのネットワーク マッピングと、ターゲット リージョンからソース リージョンへのネットワーク マッピングが自動的に作成されます。
- 既定では、Site Recovery では、ソース ネットワークと同じターゲット リージョンにネットワークが作成されます。 Site Recovery では、ソース ネットワークの名前にサフィックスとして **-asr** が追加されます。 ターゲット ネットワークをカスタマイズできます。
- ネットワーク マッピングが既に行われている場合、レプリケーションを有効にするときに、ターゲット仮想ネットワークを変更することはできません。 ターゲット仮想ネットワークを変更するには、既存のネットワーク マッピングを変更する必要があります。
- リージョン A からリージョン B へのネットワーク マッピングを変更する場合は、リージョン B からリージョン A へのネットワーク マッピングも必ず変更してください。

## <a name="specify-a-subnet"></a>サブネットを指定する

ターゲット VM のサブネットは、ソース VM のサブネットの名前に基づいて選択されます。

- ソース VM サブネットと同じ名前のサブネットをターゲット ネットワークで利用できる場合は、そのサブネットがターゲット VM に対して設定されます。
- ターゲット ネットワークに同じ名前のサブネットが存在しない場合は、アルファベット順で最初のサブネットがターゲット サブネットとして設定されます。
- VM の **[コンピューティングとネットワーク]** の設定でこれを変更できます。

    ![[コンピューティングとネットワーク] の [コンピューティングのプロパティ] ウィンドウ](./media/site-recovery-network-mapping-azure-to-azure/modify-subnet.png)


## <a name="set-up-ip-addressing-for-target-vms"></a>ターゲット VM の IP アドレス指定を設定する

ターゲット仮想マシンの各 NIC の IP アドレスは、次のように構成されます。

- **DHCP**:ソース VM の NIC が DHCP を使用する場合は、ターゲット VM の NIC も DHCP を使用するように設定されます。
- **静的 IP アドレス**:ソース VM の NIC が静的 IP アドレス指定を使用する場合は、ターゲット VM の NIC も静的 IP アドレスを使用します。


## <a name="ip-address-assignment-during-failover"></a>フェールオーバー時の IP アドレスの割り当て

**ソースとターゲットのサブネット** | **詳細**
--- | ---
同じアドレス空間 | ソース VM の NIC の IP アドレスは、ターゲット VM の NIC の IP アドレスとして設定されます。<br/><br/> このアドレスが使用できない場合は、次に使用可能な IP アドレスがターゲットとして設定されます。
異なるアドレス空間<br/><br/> ターゲット サブネット内の次に使用可能な IP アドレスがターゲット VM の NIC アドレスとして設定されます。



## <a name="ip-address-assignment-during-test-failover"></a>テスト フェールオーバー時の IP アドレスの割り当て

**ターゲット ネットワーク** | **詳細**
--- | ---
ターゲット ネットワークがフェールオーバー VNet の場合 | - ターゲット IP アドレスは静的ですが、フェールオーバー用に予約されている同じ IP アドレスにはなりません。<br/><br/>  - 割り当てられるアドレスは、サブネット範囲の末尾から順に、次に使用可能なアドレスとなります。<br/><br/> 例: ソース IP アドレスが 10.0.0.19 で、フェールオーバー ネットワークで範囲 10.0.0.0/24 が使用される場合、ターゲット VM に対して割り当てられる次の IP アドレスは 10.0.0.254 です。
ターゲット ネットワークがフェールオーバー VNet ではない場合 | - ターゲット IP アドレスは静的で、フェールオーバー用に予約されているのと同じ IP アドレスになります。<br/><br/>  - 同じ IP アドレスが既に割り当てられている場合、IP アドレスは各サブネット範囲で次に利用できる IP になります。<br/><br/> 例: ソースの静的 IP アドレスが 10.0.0.19 で、フェールオーバーがフェールオーバー ネットワークではないネットワーク上で行われる場合 (範囲は 10.0.0.0/24)、ターゲットの静的 IP アドレスは 10.0.0.0.19 (これが使用可能な場合) となり、使用可能でない場合は 10.0.0.254 となります。

- フェールオーバー VNet は、ディザスター リカバリーの設定時に選択するターゲット ネットワークです。
- テスト フェールオーバーには必ず非運用環境のネットワークを使用することをお勧めします。
- VM の **[コンピューティングとネットワーク]** の設定でターゲット IP アドレスを変更できます。


## <a name="next-steps"></a>次の手順

- Azure VM ディザスター リカバリーについては、[ネットワーク ガイダンス](site-recovery-azure-to-azure-networking-guidance.md)をご確認ください。
- フェールオーバー後の IP アドレスの保持について[ご確認ください](site-recovery-retain-ip-azure-vm-failover.md)。

「選択されたターゲット ネットワークがフェールオーバー VNet の場合」と、2 番目の点の「選択されたターゲット ネットワークがフェールオーバー VNet とは異なるものの、フェールオーバー VNet と同じサブネット範囲の場合」