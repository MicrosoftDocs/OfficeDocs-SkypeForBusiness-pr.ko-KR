---
title: 'Lync Server 2013: Kerberos 인증 계정 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="b7f63-102">Lync Server 2013에서 Kerberos 인증 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="b7f63-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7f63-103">_**마지막으로 수정한 주제:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="b7f63-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="b7f63-104">이 절차를 성공적으로 완료 하려면 도메인 관리자 그룹의 구성원으로 서버 또는 도메인에 최소한으로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="b7f63-105">각 사이트에 대 한 Kerberos 인증 계정을 만들거나 단일 Kerberos 인증 계정을 만들어 모든 사이트에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="b7f63-106">Windows PowerShell cmdlet을 사용 하 여 각 사이트에 할당 된 계정을 식별 하는 등의 계정을 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="b7f63-107">토폴로지 작성기 및 Lync Server 2013 제어판에는 Kerberos 인증 계정이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="b7f63-108">다음 절차를 사용 하 여 Kerberos 인증에 사용할 하나 이상의 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="b7f63-109">Kerberos 계정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b7f63-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="b7f63-110">Domain Admins 그룹의 구성원으로 Lync Server 2013를 실행 하는 도메인의 컴퓨터 또는 관리 도구가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="b7f63-111">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b7f63-112">명령줄에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="b7f63-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="b7f63-114">Active Directory 사용자 및 컴퓨터를 열고 **사용자** 컨테이너를 확장 한 다음 사용자 계정에 대 한 컴퓨터 개체가 컨테이너에 있는지 확인 하 여 컴퓨터 개체를 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f63-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

