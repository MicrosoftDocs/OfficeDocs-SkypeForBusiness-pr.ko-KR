---
title: 추가 기능 관리
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 964716509feb0bf1101181693e5ab777de6736ab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-add-ins"></a>추가 기능 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

새 영구 채팅 서버 추가 기능을 만들려면

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a>추가 기능 만들기, 가져오기, 설정 또는 제거

새로운 추가 기능을 만들려면

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> PersistentChatPoolFqdn &lt; String &gt; 은 영구 채팅 서버 풀이 둘 이상 있는 경우에만 필요 합니다.



</div>

추가 기능을 가져오려면

    Get-CsPersistentChatAddin -Identity <String>]

또는

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

추가 기능을 설정하려면

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

또는

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

추가 기능을 제거하려면

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

또는

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

