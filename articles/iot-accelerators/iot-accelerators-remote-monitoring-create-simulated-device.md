---
title: IoT リモート監視を使用したデバイス シミュレーション - Azure | Microsoft Docs
description: このハウツー ガイドでは、リモート監視ソリューション アクセラレータを使用したデバイス シミュレーターの使用方法について説明します。
author: dominicbetts
manager: timlt
ms.author: dobett
ms.service: iot-accelerators
services: iot-accelerators
ms.date: 02/08/2019
ms.topic: conceptual
ms.openlocfilehash: 9d15174bc777b20eb7f3988dc33be15c46b1cc43
ms.sourcegitcommit: 39397603c8534d3d0623ae4efbeca153df8ed791
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "56098138"
---
# <a name="create-and-test-a-new-simulated-device"></a>新しいシミュレートされたデバイスの作成とテスト

リモート監視ソリューション アクセラレータを使用すると、独自のシミュレーションされたデバイスを定義できます。 この記事では、新しいシミュレートされた lightbulb デバイスを定義し、それをローカルでテストする方法を説明します。 ソリューション アクセラレータには、chiller や truck などのシミュレートされたデバイスがあります。 ただし、実際のデバイスを展開する前に、独自のシミュレートされたデバイスを定義して IoT ソリューションをテストすることができます。

> [!NOTE]
> この記事では、デバイス シミュレーション サービスでホストされているシミュレートされたデバイスを使用する方法について説明します。 実際のデバイスを作成する場合は、「[デバイスをリモート監視ソリューション アクセラレータに接続する](iot-accelerators-connecting-devices.md)」を参照してください。

このハウツー ガイドでは、デバイス シミュレーション マイクロサービスをカスタマイズする方法について説明します。 このマイクロサービスは、リモート監視ソリューション アクセラレータの一部です。 デバイス シミュレーション機能を説明するために、このハウツー ガイドでは、Contoso IoT アプリケーションの 2 つのシナリオを使用しています。

[!INCLUDE [iot-solution-accelerators-create-device](../../includes/iot-solution-accelerators-create-device.md)]

## <a name="next-steps"></a>次の手順

このガイドでは、カスタムのシミュレートされたデバイスの種類を作成し、デバイス シミュレーション マイクロサービスをローカルで実行してテストする方法について説明しました。

推奨される次の手順は、カスタムのシミュレートされたデバイスの種類を[リモート監視ソリューション アクセラレータ](iot-accelerators-remote-monitoring-deploy-simulated-device.md)に展開する方法を学習することです。
