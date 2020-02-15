---
title: 'Lync Server 2013: 영구 채팅 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c43bfaf3b40a746f09a000cb089509b589e39e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="5fa73-102">Lync Server 2013에서 영구 채팅 서버 구성</span><span class="sxs-lookup"><span data-stu-id="5fa73-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fa73-103">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5fa73-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5fa73-104">새 영구 채팅 구성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5fa73-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="5fa73-105">영구 채팅 구성을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="5fa73-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="5fa73-106">영구 채팅 구성을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="5fa73-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="5fa73-107">영구 채팅 구성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5fa73-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="5fa73-108">Lync Server 2013의 경우 모든 웹 서비스 트래픽은 Lync Server 2013, 프런트 엔드 서버에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fa73-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="5fa73-109">따라서 영구 채팅 서버의 gcweb01 주소는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fa73-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="5fa73-110">원격 사용자의 *외부* 웹 사이트가 아니라 *내부* 웹 사이트에 대해서만 파일 업로드/다운로드 웹 서비스를 제공하기 때문에 내부 웹 서비스 액세스도 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fa73-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

