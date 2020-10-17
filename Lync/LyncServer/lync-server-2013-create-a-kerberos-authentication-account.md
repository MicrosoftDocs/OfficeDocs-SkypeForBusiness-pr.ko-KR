---
title: 'Lync Server 2013: Kerberos 인증 계정 만들기'
description: 'Lync Server 2013: Kerberos 인증 계정을 만듭니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f8e87a8ffcc95af4a44e516ac4e1f4d635d737
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542134"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="e8d52-103">Lync Server 2013에서 Kerberos 인증 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="e8d52-103">Create a Kerberos authentication account in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8d52-104">_**마지막으로 수정 된 항목:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="e8d52-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="e8d52-105">이 절차를 성공적으로 완료하려면 최소한 Domain Admins 그룹 구성원으로 서버나 도메인에 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d52-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="e8d52-106">각 사이트에 대해 Kerberos 인증 계정을 만들 수도 있고, 단일 Kerberos 인증 계정을 만들어 모든 사이트에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d52-106">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="e8d52-107">Windows PowerShell cmdlet을 사용 하 여 각 사이트에 할당 된 계정을 식별 하는 등의 계정을 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d52-107">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="e8d52-108">토폴로지 작성기 및 Lync Server 2013 제어판은 Kerberos 인증 계정을 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d52-108">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="e8d52-109">다음 절차에 따라 Kerberos 인증에 사용할 하나 이상의 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e8d52-109">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="e8d52-110">Kerberos 계정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e8d52-110">To create a Kerberos account</span></span>

1.  <span data-ttu-id="e8d52-111">Domain Admins 그룹의 구성원으로 서 Lync Server 2013를 실행 하는 도메인의 컴퓨터 또는 관리 도구가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d52-111">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="e8d52-112">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d52-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e8d52-113">명령줄에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d52-113">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="e8d52-114">예:</span><span class="sxs-lookup"><span data-stu-id="e8d52-114">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="e8d52-115">컴퓨터 개체가 만들어졌는지 확인합니다. 이렇게 하려면 Active Directory 사용자 및 컴퓨터를 열고 **사용자** 컨테이너를 확장한 다음 사용자 계정의 컴퓨터 개체가 컨테이너에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d52-115">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

