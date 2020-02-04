---
title: 'Lync Server 2013: Lync-Skype 연결 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0125ff4719cd3dfeb65353df747395e596b45dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="a4322-102">Lync Server 2013에서 Lync-Skype 연결 사용</span><span class="sxs-lookup"><span data-stu-id="a4322-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4322-103">_**마지막으로 수정한 주제:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="a4322-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="a4322-104">프로비저닝 요청을 제출 하 고 나면 lync-Skype 연결을 구성 하는 데 필요한 Lync Server 환경 및 관리 작업에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="a4322-105">이 섹션에서는 Lync Server 관리자가 Lync Server를 배포 하 고 외부 액세스를 구성한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="a4322-106">Lync Server에 대 한 외부 액세스를 구성 하는 방법에 대 한 자세한 내용은 lync server [2013에서 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 및 [lync server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4322-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="a4322-107">Lync에서 Skype 연결을 위한 Lync Server 환경을 준비 하려면 Lync Server 관리자가 다음 세 가지 작업을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="a4322-108">1 \.</span><span class="sxs-lookup"><span data-stu-id="a4322-108">1\.</span></span> <span data-ttu-id="a4322-109">페더레이션 및 PIC 구성</span><span class="sxs-lookup"><span data-stu-id="a4322-109">Configure Federation and PIC</span></span>

<span data-ttu-id="a4322-110">페더레이션은 Skype 사용자가 조직의 Lync 사용자와 통신할 수 있도록 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="a4322-111">PIC (공용 인스턴트 메시징 연결)는 페더레이션 클래스 이며 Lync 사용자가 Skype 사용자와 통신할 수 있도록 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="a4322-112">페더레이션 및 PIC는 아래 표시 된 Lync Server 제어판을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="a4322-113">![PIC 표시](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC 표시")</span><span class="sxs-lookup"><span data-stu-id="a4322-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4322-114">PIC federation는 실시간 통신 서버 2005 SP1 또는 Office Communications Server 2007에서 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="a4322-115">PIC 페더레이션에 대해 지원 되는 플랫폼에는 Lync Server 2013, Lync Server 2010 및 Office Communications Server 2007 R2가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="a4322-116">2 \입니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-116">2\.</span></span> <span data-ttu-id="a4322-117">페더레이션 사용자 액세스를 지원 하도록 하나 이상의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="a4322-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="a4322-118">관리자는 Lync Server 제어판을 사용 하 여 Skype 사용자가 내부 Lync Server 사용자와 공동 작업을 할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="a4322-119">![정책](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "정책")</span><span class="sxs-lookup"><span data-stu-id="a4322-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="a4322-120">3 \.</span><span class="sxs-lookup"><span data-stu-id="a4322-120">3\.</span></span> <span data-ttu-id="a4322-121">Lync에 대 한 Skype PIC 공급자 설정 구성</span><span class="sxs-lookup"><span data-stu-id="a4322-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="a4322-122">Lync Server Management Shell을 사용 하는 경우 관리자는 Lync 클라이언트 정책을 구성 하 여 Skype를 추가 PIC 공급자로 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4322-123">공용 IM 연결을 지원 하기 위해 PIC (공용 메신저 연결) 서비스 공급자의 사용자는 적어도 하나 이상의 정책 (이 절차의 앞부분 2 단계)을 구성할 때까지 조직의 IM 또는 오디오 또는 비디오 회의에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="a4322-124">페더레이션 및 PIC를 구성 하려면에서 [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)"페더레이션 및 공용 IM 연결 사용 또는 사용 안 함"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4322-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="a4322-125">페더레이션 사용자 액세스를 지원 하도록 정책을 하나 이상 구성 하려면에서 [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)"공용 사용자 액세스를 제어 하도록 정책 구성"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4322-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="a4322-126">**기존 Messenger 또는 Skype PIC 공급자를 편집 하 고 Skype에 맞게 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="a4322-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="a4322-127">Lync Server 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="a4322-128">다음 두 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4322-129">환경에 PIC 공급자가 아직 없고 새 PIC 공급자를 만드는 경우 <STRONG>CsPublicProvider</STRONG> cmdlet을 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4322-130">Lync Server 2013 CU5 &amp; lync 데스크톱 클라이언트에 추가 됨 OFFICE 2013 SP1의 NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList는 lync 사용자가 타사 도메인을 식별 하 여 skype에 연결 하는 데 필요한 skype 연락처 (예: 사용자 (contoso) @msn .의 형식)를 개선 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="a4322-131">이 새로운 설정을 사용 하면 NameDecorationExcludedDomainList에 도메인이 포함 되지 않은 경우 "Skype 연락처 추가" 대화 상자에 NameDecorationRoutingDomain (msn.com로 설정 되어야 함)의 주소 사용자 입력에 대 한 자동 서식 지정이 허용 됩니다 ( 현재 msn.com, live.com, Hotmail.com, outlook.com)를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="a4322-132">Lync 클라이언트에서 이제 Skype를 PIC 공급자로 선택 하 고 Microsoft 계정을 지정 하 여 Skype 클라이언트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="a4322-133">또한 Microsoft 계정으로 병합 및 로그인 한 Skype 사용자는 연락처 요청을 Lync 사용자에 게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="a4322-134">Microsoft 계정에 대 한 자세한 내용은 [microsoft 계정 이란?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4322-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="a4322-135">Lync에 클라이언트를 추가 하는 방법에 대 한 자세한 내용은 [최종 사용자로 Lync Server 2013에서 lync-Skype 연결 사용](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4322-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="a4322-136">![Skype 대화 상대 추가](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype 대화 상대 추가")</span><span class="sxs-lookup"><span data-stu-id="a4322-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="a4322-137">호스팅된 공급자를 수정 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)"호스트 된 SIP 페더레이션 공급자 만들기 또는 편집"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4322-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="a4322-138">이렇게 하면 서버에서 수행 해야 하는 관리 작업이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="a4322-139">이제 Lync-Skype 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4322-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

