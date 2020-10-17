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
ms.openlocfilehash: fc6bb0368b97e41402f2e0abf0834cf23f078c08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514815"
---
# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="8fb3c-102">Lync Server 2013에서 기본 그림 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="8fb3c-102">Configuring default picture options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fb3c-103">_**마지막으로 수정 된 항목:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="8fb3c-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="8fb3c-104">기본적으로 사용자의 사진은 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fb3c-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="8fb3c-105">사용자가 사진을 숨기려는 경우 Lync 클라이언트에서 **내 그림 숨기기** 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb3c-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="8fb3c-106">그러나 다른 Office 응용 프로그램에서는이 설정이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fb3c-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="8fb3c-107">사용자가이 기능을 해제 한 경우에도 그림을 표시할 가능성이 있는 경우에는 사용자의 사진이 기본적으로 표시 되지 않도록 Lync 그림 표시 설정을 전역적으로 또는 사이트 또는 서비스에 대해 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb3c-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="8fb3c-108">다음 Lync Server 관리 셸 cmdlet을 사용 하면 클라이언트에서 **내 그림 표시** 옵션을 명시적으로 선택 하지 않으면 사용자의 사진이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb3c-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="8fb3c-109">이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서에서 [get-csprivacyconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fb3c-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

