---
title: 'Lync Server 2013: VDI에 대 한 환경 준비'
description: 'Lync Server 2013: VDI에 대 한 환경 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e90b9e0f09d3082a28406f1a1dc715285ee4d7e3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579914"
---
# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a><span data-ttu-id="70e2f-103">VDI에 대 한 Lync Server 2013 환경 준비</span><span class="sxs-lookup"><span data-stu-id="70e2f-103">Preparing your Lync Server 2013 environment for VDI</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70e2f-104">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="70e2f-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="70e2f-105">Lync VDI 플러그 인의 환경을 준비 하려면 관리자가 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e2f-105">To prepare the environment for the Lync VDI plug-in, the administrator must perform the following steps.</span></span>

1.  <span data-ttu-id="70e2f-106">Lync Server 2013에서 모든 VDI 사용자에 대해 EnableMediaRedirection이 TRUE로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e2f-106">In Lync Server 2013, ensure that EnableMediaRedirection is set to TRUE for all VDI users.</span></span> <span data-ttu-id="70e2f-107">자세한 내용은 [새-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 및 [설정-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70e2f-107">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

2.  <span data-ttu-id="70e2f-108">데이터 센터 컴퓨터에서 모든 가상 컴퓨터에 Lync 2013 클라이언트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e2f-108">On the data center computer, install the Lync 2013 client on all virtual machines.</span></span>

3.  <span data-ttu-id="70e2f-109">로컬 컴퓨터에서 Lync VDI 플러그 인을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e2f-109">On the local computers, install the Lync VDI plug-in.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

