---
title: トラブルシューティング:ダウンロードした Azure Active Directory アクティビティ ログにデータが見つからない | Microsoft Docs
description: ダウンロードした Azure Active Directory アクティビティ ログにデータが見つからない問題の解決策を提供します。
services: active-directory
documentationcenter: ''
author: priyamohanram
manager: daveba
editor: ''
ms.assetid: ffce7eb1-99da-4ea7-9c4d-2322b755c8ce
ms.service: active-directory
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: identity
ms.subservice: report-monitor
ms.date: 11/13/2018
ms.author: priyamo
ms.reviewer: dhanyahk
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1ba5f803f59263f9bfebfd4ec8635d5cdd6d90a0
ms.sourcegitcommit: 301128ea7d883d432720c64238b0d28ebe9aed59
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56171776"
---
# <a name="i-cant-find-all-the-data-in-the-azure-active-directory-activity-logs-i-downloaded"></a>ダウンロードした Azure Active Directory アクティビティ ログにすべてのデータが表示されません。

## <a name="symptoms"></a>現象

アクティビティ ログ (監査またはサインイン) をダウンロードしましたが、選択した期間のレコードがまったく表示されません。 なぜですか? 

 ![レポート](./media/troubleshoot-missing-data-download/01.png)
 
## <a name="cause"></a>原因

Azure Portal でアクティビティ ログをダウンロードする場合は、新しい順に並べ替えられた最新の 5000 件のレコードに制限されます。 

## <a name="resolution"></a>解決策

[Azure AD Reporting API](concept-reporting-api.md) を利用すると、任意の時点のレコードを最大 100 万件取得できます。 Reporting API を呼び出して、増分方式で一定期間 (たとえば、毎日や毎週) のレコードを取得する[スクリプトを定期的に実行する](tutorial-signin-logs-download-script.md)ことをお勧めします。 

## <a name="next-steps"></a>次の手順

* [Azure Active Directory レポートの FAQ](reports-faq.md)

