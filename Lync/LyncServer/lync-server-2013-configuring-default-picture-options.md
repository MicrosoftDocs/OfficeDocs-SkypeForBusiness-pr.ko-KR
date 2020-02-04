---
title: 'Lync Server 2013: 기본 그림 옵션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e551d069da9a3afb7a884c28096dd97ab3702539
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="ac1ad-102">Lync Server 2013에서 기본 그림 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ac1ad-102">Configuring default picture options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac1ad-103">_**마지막으로 수정한 주제:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="ac1ad-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="ac1ad-104">기본적으로 사용자의 그림이 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac1ad-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="ac1ad-105">사용자가 사진을 숨기려는 경우 Lync 클라이언트에서 **내 사진 숨기기** 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac1ad-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="ac1ad-106">그러나 일부 다른 Office 응용 프로그램에서는이 설정이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac1ad-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="ac1ad-107">사용자가 해제 한 경우에도 그림을 표시할 수 있는 경우에는 사용자의 그림이 기본적으로 표시 되지 않도록 Lync 그림 표시 설정을 전역 또는 사이트 또는 서비스에 변경 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac1ad-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="ac1ad-108">다음 Lync Server 관리 셸 cmdlet을 사용 하 여 클라이언트에서 **내 사진 표시** 옵션을 명시적으로 선택 하지 않으면 사용자의 사진이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac1ad-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="ac1ad-109">이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac1ad-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

