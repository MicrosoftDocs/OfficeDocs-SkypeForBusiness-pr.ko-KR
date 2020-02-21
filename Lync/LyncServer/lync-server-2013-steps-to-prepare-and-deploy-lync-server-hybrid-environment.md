---
title: 'Lync Server 2013: Lync Server 하이브리드 환경을 준비 및 배포 하기 위한 단계'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 207cb9b8435294abeac12f67506eb356a6ca73c6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="5f9e2-102">Lync Server 2013 하이브리드 환경을 준비 및 배포 하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="5f9e2-102">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f9e2-103">_**마지막으로 수정 된 항목:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="5f9e2-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="5f9e2-104">다음 표에서는 비즈니스용 Skype Online 및 Microsoft Office 365을 사용 하 여 하이브리드 배포를 위해 환경을 준비 하는 데 필요한 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-104">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f9e2-105">완료 여부</span><span class="sxs-lookup"><span data-stu-id="5f9e2-105">Completed?</span></span></th>
<th><span data-ttu-id="5f9e2-106">단계</span><span class="sxs-lookup"><span data-stu-id="5f9e2-106">Step</span></span></th>
<th><span data-ttu-id="5f9e2-107">설명</span><span class="sxs-lookup"><span data-stu-id="5f9e2-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="5f9e2-108">Office 365에 대 한 테 넌 트 계정 만들기 및 Lync Online 사용</span><span class="sxs-lookup"><span data-stu-id="5f9e2-108">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="5f9e2-109">Office <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">365</a>의 office 365 및 Lync Online에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-109">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="5f9e2-110">사용자 환경이 Office 365에 대 한 준비가 되었는지 확인 하려면 <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">시스템 요구 사항을</a>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-110">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="5f9e2-111">Office 365을 설정 하는 방법에 대 한 자세한 내용은 <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">office 365 시작</a> 및 <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">office 설정 365</a>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-111">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="5f9e2-112">도메인 추가 및 소유권 확인</span><span class="sxs-lookup"><span data-stu-id="5f9e2-112">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="5f9e2-113">도메인은 <em>베 니 티 도메인이</em>라고도 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-113">Your domain is sometimes also referred to as your <em>vanity domain</em>.</span></span> <span data-ttu-id="5f9e2-114">Office 365 테 넌 트에 도메인을 추가 하 고 해당 단계에 따라 Office 365 도메인의 유효성을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-114">You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="5f9e2-115">이는 사용자가 도메인의 소유자 인지 확인 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-115">This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="5f9e2-116">Office 365 테 넌 트에 도메인을 추가 하려면 <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">office 365에 도메인 추가</a>에 설명 된 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-116">To add your domain to your Office 365 tenant, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="5f9e2-117">Office 365 서비스에 대 한 DNS 레코드 편집을 포함 &quot;하 여 항목의 각 섹션에 있는 모든 단계를 완료 합니다.&quot;</span><span class="sxs-lookup"><span data-stu-id="5f9e2-117">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="5f9e2-118">환경 준비 확인</span><span class="sxs-lookup"><span data-stu-id="5f9e2-118">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="5f9e2-119">Office 365 설정 도우미를 사용 하 여 Office 365 배포를 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-119">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="5f9e2-120">자세한 내용은 <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Setup Assistant를 사용 하 여 Office 365 준비 상태 확인</a>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-120">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="5f9e2-121">도구를 사용 하 고 Office 365을 배포 하는 방법에 대 한 자세한 내용은 <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">office 365 배포 가이드</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-121">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="5f9e2-122">Active Directory 동기화 준비</span><span class="sxs-lookup"><span data-stu-id="5f9e2-122">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="5f9e2-123">Active Directory 동기화를 사용 하면 온-프레미스 Active Directory가 계속 해 서 Office 365와 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-123">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="5f9e2-124">이렇게 하면 각 사용자 계정 및 그룹의 동기화 된 버전을 만들 수 있을 뿐만 아니라 로컬 Microsoft Exchange 서버 환경에서 Microsoft Exchange Online으로 GAL (전체 주소 목록)을 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-124">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="5f9e2-125">사용자가 Lync Online으로 이동 하지 않은 경우에도 조직의 모든 Lync 사용자에 대 한 AD 계정을 온-프레미스 및 온라인 Lync 배포 사이에 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-125">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="5f9e2-126">모든 사용자를 동기화 하지 않으면 조직에서 온-프레미스 및 온라인 사용자 간의 통신이 예상 대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-126">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="5f9e2-127">Active Directory 동기화를 위해 환경을 준비 하려면 single sign-on 설정을 비롯 하 여 <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">디렉터리 동기화 로드맵</a>에 설명 된 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-127">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="5f9e2-128">AD FS (Active Directory Federation Services)에 대 한 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="5f9e2-128">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="5f9e2-129">Office 365의 id 페더레이션에 사용 되는 인증서를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-129">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="5f9e2-130">자세한 내용은 <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">검사 목록: AD fs를 사용 하 여 single sign-on을 구현 하 고 관리 하</a>는 데 사용할 Ad fs 계획 및 배포의 "페더레이션 서버 인증서" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-130">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="5f9e2-131">AD FS에 대 한 인증서 할당</span><span class="sxs-lookup"><span data-stu-id="5f9e2-131">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="5f9e2-132">Office 365와의 id 페더레이션에 사용 되는 인증서를 만든 후에는이를 설치 하 고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-132">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="5f9e2-133">파일럿 사용자를 비즈니스용 Skype 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="5f9e2-133">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="5f9e2-134">비즈니스용 Skype Online에 대 한 환경을 준비 하 고 구성 하는 단계를 완료 한 후 파일럿 사용자를 Lync Online으로 이동 하는 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-134">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="5f9e2-135"><a href="lync-server-2013-move-users-to-lync-online.md">Lync Server 2013에서 사용자를 Lync Online으로 이동을</a>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-135">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="5f9e2-136">하이브리드 배포에서 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="5f9e2-136">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="5f9e2-137">하이브리드 배포에서 사용자를 관리 하는 방법에 대 한 자세한 내용은 <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">하이브리드 Lync Server 2013 배포에서 사용자</a>관리를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-137">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

