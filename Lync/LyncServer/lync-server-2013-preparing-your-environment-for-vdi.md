---
title: 'Lync Server 2013: VDI에 대한 환경 준비'
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
ms.openlocfilehash: 57a3fb2563e287f24d49c23a468b4a44528707b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a><span data-ttu-id="bf304-102">VDI에 대한 Lync Server 2013 환경 준비</span><span class="sxs-lookup"><span data-stu-id="bf304-102">Preparing your Lync Server 2013 environment for VDI</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf304-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="bf304-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="bf304-104">Lync VDI 플러그 인에 대 한 환경을 준비 하려면 관리자가 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf304-104">To prepare the environment for the Lync VDI plug-in, the administrator must perform the following steps.</span></span>

1.  <span data-ttu-id="bf304-105">Lync Server 2013에서 모든 VDI 사용자에 대해 EnableMediaRedirection가 TRUE로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf304-105">In Lync Server 2013, ensure that EnableMediaRedirection is set to TRUE for all VDI users.</span></span> <span data-ttu-id="bf304-106">자세한 내용은 [새 csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 및 [Set csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf304-106">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

2.  <span data-ttu-id="bf304-107">데이터 센터 컴퓨터에서 모든 가상 컴퓨터에 Lync 2013 클라이언트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf304-107">On the data center computer, install the Lync 2013 client on all virtual machines.</span></span>

3.  <span data-ttu-id="bf304-108">로컬 컴퓨터에서 Lync VDI 플러그 인을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf304-108">On the local computers, install the Lync VDI plug-in.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

