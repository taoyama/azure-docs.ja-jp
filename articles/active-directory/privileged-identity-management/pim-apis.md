---
title: Azure AD Privileged Identity Management (PIM) 向けの Microsoft Graph API (プレビュー) | Microsoft Docs
description: Azure Active Directory Privileged Identity Management (PIM) 向けの Microsoft Graph API (プレビュー) の使用に関する情報を提供します。
services: active-directory
documentationcenter: ''
author: rolyon
manager: mtillman
editor: ''
ms.service: active-directory
ms.workload: identity
ms.subservice: pim
ms.topic: overview
ms.date: 11/13/2018
ms.author: rolyon
ms.custom: pim
ms.collection: M365-identity-device-management
ms.openlocfilehash: 97b548d199dd98a0f8c788c8c50ba618f721f4ab
ms.sourcegitcommit: 301128ea7d883d432720c64238b0d28ebe9aed59
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56183940"
---
# <a name="microsoft-graph-apis-for-pim-preview"></a>PIM 向けの Microsoft Graph API (プレビュー)

Azure portal を使用して Azure AD Privileged Identity Management (PIM) で実行できるタスクのほとんどは、[Microsoft Graph API](https://developer.microsoft.com/graph/docs/concepts/overview) を使用して実行することもできます。 この記事では、PIM 向けの Microsoft Graph API を使用する際のいくつかの重要な概念について説明します。 Microsoft Graph API の詳細については、[Azure AD Privileged Identity Management API のリファレンス](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/privilegedidentitymanagement_root)に関するページをご確認ください。

> [!IMPORTANT]
> Microsoft Graph でベータ版の API はプレビュー段階であり、変更されることがあります。 実稼働アプリケーションにおけるこれらの API の使用はサポートされていません。

## <a name="required-permissions"></a>必要なアクセス許可

PIM 向けの Microsoft Graph API を呼び出すには、以下のアクセス許可が **1 つまたは複数**必要です。

- `Directory.AccessAsUser.All`
- `Directory.Read.All`
- `Directory.ReadWrite.All`
- `PrivilegedAccess.ReadWrite.AzureAD`

### <a name="set-permissions"></a>アクセス許可を設定する

アプリケーションが PIM 向けの Microsoft Graph API を呼び出すには、それらが必要なアクセス許可を備えていなければなりません。 必要なアクセス許可を指定する最も簡単な方法は、[Azure AD 同意フレームワーク](../develop/consent-framework.md)を使用することです。

### <a name="set-permissions-in-graph-explorer"></a>Graph エクスプローラーでアクセス許可を設定する

ご自分の呼び出しをテストするために Graph エクスプローラーを使用している場合は、お客様はツール内でアクセス許可を指定できます。

1. グローバル管理者として [Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)にサインインします。

1. **[アクセス許可の変更]** をクリックします。

    ![Graph エクスプローラー - アクセス許可の変更](./media/pim-apis/graph-explorer.png)

1. 含めたいアクセス許可の横にあるチェックマークをオンにします。 `PrivilegedAccess.ReadWrite.AzureAD` は、Graph エクスプローラーではまだ使用できません。

    ![Graph エクスプローラー - アクセス許可の変更](./media/pim-apis/graph-explorer-modify-permissions.png)

1. **[アクセス許可の変更]** をクリックして、アクセス許可の変更を適用します。

## <a name="next-steps"></a>次の手順

- [Azure AD Privileged Identity Management API のリファレンス](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/privilegedidentitymanagement_root)
