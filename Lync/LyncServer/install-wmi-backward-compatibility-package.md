---
title: WMI 이전 버전과의 호환성 패키지 설치
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35be17aa08cf26f93a9d4002b23dacdfb35c5143
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="4b55b-102">WMI 이전 버전과의 호환성 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="4b55b-102">Install WMI Backward Compatibility package</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b55b-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4b55b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4b55b-104">WMI 이전 버전과의 호환성 패키지를 설치하지 않고 토폴로지 작성기 병합 마법사를 실행하려고 하면 다음과 같은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b55b-104">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="4b55b-105">![WMI 오류 메시지](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 오류 메시지")</span><span class="sxs-lookup"><span data-stu-id="4b55b-105">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="4b55b-106">WMI 이전 버전과의 호환성 패키지를 설치하지 않고 **Merge-CsLegacytopology** cmdlet을 실행하려고 하면 다음과 같은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b55b-106">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="4b55b-107">![Windows PowerShell WMI 공급자 오류](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 공급자 오류")</span><span class="sxs-lookup"><span data-stu-id="4b55b-107">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="4b55b-108">WMI 이전 버전과의 호환성 패키지를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="4b55b-108">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="4b55b-109">설치 미디어에서 \\ SETUP \\ AMD64 setupOCSWMIBC.MSI으로 이동 \\ \\ 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b55b-109">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="4b55b-110">OCSWMIBC.MSI를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4b55b-110">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b55b-111">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run.</span><span class="sxs-lookup"><span data-stu-id="4b55b-111">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run.</span></span> <span data-ttu-id="4b55b-112">However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span><span class="sxs-lookup"><span data-stu-id="4b55b-112">However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b55b-113">OCSWMIBC.msi은 Lync Server 2013 핵심 구성 요소와 Lync Server 2013 관리 셸이 설치 되어 있는 도메인의 컴퓨터에 설치할 수 있으며 Office Communications Server 2007 R2 토폴로지 (WMI 공급자에 게 AD DS (Active Directory 도메인 서비스) 및 SQL Server)에 대 한 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b55b-113">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

