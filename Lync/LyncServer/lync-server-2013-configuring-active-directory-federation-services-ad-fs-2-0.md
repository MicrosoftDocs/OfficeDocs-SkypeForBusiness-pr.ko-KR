---
title: 'Lync Server 2013: AD FS 2.0 (Active Directory Federation Services) 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba3a74f59bc996defcd9baee9162d034ab2178eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="2ccb7-102">Lync Server 2013에 대 한 AD FS 2.0 (Active Directory Federation Services) 구성</span><span class="sxs-lookup"><span data-stu-id="2ccb7-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ccb7-103">_**마지막으로 수정 된 항목:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="2ccb7-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="2ccb7-104">다음 섹션에서는 다단계 인증을 지원 하도록 AD FS 2.0 (Active Directory Federation Services)를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="2ccb7-105">AD FS 2.0을 설치 하는 방법에 대 한 자세한 내용은 AD FS 2.0 단계별 및 How To 가이드를 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span><span class="sxs-lookup"><span data-stu-id="2ccb7-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="2ccb7-106">AD FS 2.0을 설치할 때 Windows Server Manager를 사용 하 여 Active Directory Federation Services 역할을 추가 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="2ccb7-107">대신,에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>Active Directory Federation Services 2.0 rtw 패키지를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="2ccb7-108">**2 단계 인증을 사용 하도록 AD FS를 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="2ccb7-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="2ccb7-109">도메인 관리자 계정을 사용 하 여 AD FS 2.0 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="2ccb7-110">Windows PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="2ccb7-111">Windows PowerShell 명령줄에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="2ccb7-112">다음 명령을 실행 하 여 수동 인증을 사용 하도록 설정 되는 Lync Server 2013에 대 한 누적 업데이트를 포함 하는 각 Lync Server 2013:7 2013 월, Enterprise 풀 및 Standard Edition server에 대 한 파트너 관계를 설정 합니다. 배포와 관련 한 서버 이름:</span><span class="sxs-lookup"><span data-stu-id="2ccb7-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="2ccb7-113">관리 도구 메뉴에서 AD FS 2.0 관리 콘솔을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="2ccb7-114">**트러스트 관계** \> **신뢰 당사자 트러스트**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="2ccb7-115">Lync server 2013에 대 한 누적 업데이트, 2013 년 7 2013 월 엔터프라이즈 풀 또는 Standard Edition Server에 대 한 새 신뢰가 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="2ccb7-116">다음 명령을 실행 하 여 Windows PowerShell을 사용 하 여 신뢰 당사자 트러스트에 대 한 발급 권한 부여 규칙을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="2ccb7-117">다음 명령을 실행 하 여 Windows PowerShell을 사용 하 여 신뢰 당사자 트러스트에 대 한 발급 변환 규칙을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="2ccb7-118">AD FS 2.0 관리 콘솔에서 신뢰 당사자 트러스트를 마우스 오른쪽 단추로 클릭 하 고 **클레임 규칙 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="2ccb7-119">**발급 권한 부여 규칙** 탭을 선택 하 고 새 인증 규칙이 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="2ccb7-120">**발급 변환 규칙** 탭을 선택 하 고 새 변환 규칙이 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb7-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

