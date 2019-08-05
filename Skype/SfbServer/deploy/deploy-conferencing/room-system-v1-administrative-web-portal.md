---
title: 비즈니스용 Skype 서버에서 SRS v1 관리 웹 포털 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: 비즈니스용 Skype 서버 Skype (SRS v1, 이전의 Lync 대화방 시스템) 관리 웹 포털은 조직에서 Skype 대화방 시스템 회의실을 유지 관리 하는 데 사용할 수 있는 웹 포털입니다. 관리자는 SRS v1 관리 웹 포털을 사용 하 여 오디오/비디오 장치 모니터링과 같은 디바이스 상태를 모니터링할 수 있습니다. 이 포털을 사용 하면 관리자가 진단 정보를 원격으로 수집 하 여 회의실 상태를 모니터링할 수 있습니다.
ms.openlocfilehash: 5ad4ffb08ecbc32feaa87aa2f7d48d82003e2e3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197787"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="df11a-105">비즈니스용 Skype 서버에서 SRS v1 관리 웹 포털 배포</span><span class="sxs-lookup"><span data-stu-id="df11a-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="df11a-106">비즈니스용 Skype 서버 Skype (SRS v1, 이전의 Lync 대화방 시스템) 관리 웹 포털은 조직에서 Skype 대화방 시스템 회의실을 유지 관리 하는 데 사용할 수 있는 웹 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="df11a-107">관리자는 SRS v1 관리 웹 포털을 사용 하 여 오디오/비디오 장치 모니터링과 같은 디바이스 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="df11a-108">이 포털을 사용 하면 관리자가 진단 정보를 원격으로 수집 하 여 회의실 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="df11a-109">이 기능을 사용 하려면 모든 비즈니스용 Skype Server 프런트 엔드 서버에 SRS v1 관리 웹 포털을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="df11a-110">이 가이드에서는 관리자가 SRS 관리 웹 포털을 설치 하 고 구성 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="df11a-111">이는 비즈니스용 Skype 서버 관리에 대 한 지식이 있고, 비즈니스용 Skype 서버 토폴로지를 수정할 수 있는 관리자 권한이 있는 관리자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="df11a-112">SRS v1 관리 웹 포털이 서버에 배포 된 후 관리자는 자신의 컴퓨터 또는 랩톱에서 사이트에 로그온 하 여 상태 SRS v1 장치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df11a-113">비즈니스용 [Skype 서버 2015에 대 한 Microsoft Skype 대화방 시스템 V1 관리 웹 포털](https://www.microsoft.com/en-us/download/details.aspx?id=46906)을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="df11a-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="df11a-114">이 항목의 내용:</span><span class="sxs-lookup"><span data-stu-id="df11a-114">In this topic:</span></span>

- [<span data-ttu-id="df11a-115">SRS v1 관리 웹 포털에 대 한 환경 구성</span><span class="sxs-lookup"><span data-stu-id="df11a-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="df11a-116">SRS v1 관리 웹 포털 설치</span><span class="sxs-lookup"><span data-stu-id="df11a-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="df11a-117">SRS 관리 웹 포털 사용</span><span class="sxs-lookup"><span data-stu-id="df11a-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="df11a-118">SRS v1 관리 웹 포털에 대 한 환경 구성</span><span class="sxs-lookup"><span data-stu-id="df11a-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="df11a-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="df11a-119"></span></span>

<span data-ttu-id="df11a-120">SRS v1 관리 웹 포털을 사용 하려면 다음 필수 구성 요소를 설치 하거나 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df11a-121">서버가 Kerberos 및 NTLM 인증을 모두 사용 하도록 구성 되었고 SRS가 도메인에 가입 되어 있지 않은 컴퓨터에서 실행 되는 경우 Kerberos 인증은 실패 하 고 사용자는 관리 포털에서 SRS의 상태를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="df11a-122">이 문제를 해결 하려면 ntlm 인증 또는 NTLM 및 TLS DSK 인증 (Kerberos 불포함)을 사용 하 여 서버를 구성 하거나 SRS 컴퓨터를 도메인에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="df11a-123">비즈니스용 Skype 서버 토폴로지에 비즈니스용 Skype 서버 누적 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="df11a-124">업데이트를 다운로드 하거나 포함 된 항목을 확인 하려면 [비즈니스용 Skype 서버 2015에 대 한 업데이트](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df11a-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="df11a-125">SIP 지원 Active Directory 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="df11a-126">SRS v1 관리 웹 포털은 이러한 자격 증명을 사용 하 여 비즈니스용 Skype 서버에서 정보를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="df11a-127">제공 된 예제에서 사용자 이름은 LRSApp입니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="df11a-128">이름 LRSSupportAdminGroup를 사용 하 여 Active Directory 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="df11a-129">그룹 범위가 전역 및 그룹 유형으로 보안으로 지정 된 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="df11a-130">SIP 사용이 가능이 그룹에 추가 된 사용자는 채팅방 목록을 볼 수 있도록 승인 되 고 로그 수집과 같은 특정 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="df11a-131">이름 LRSFullAccessAdminGroup를 사용 하 여 Active Directory 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="df11a-132">그룹 범위가 글로벌이 고 그룹 유형이 보안으로 설정 된 그룹을 만듭니다 .이 그룹에 추가 되는 사용자는 단일 Skype 채팅방에서 모든 관리 포털 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="df11a-133">Skype 채팅방의 일괄 관리에 대 한 지원을 포함 하려면 5 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df11a-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![보안 그룹 역할이 있는 관리 그룹 목록](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="df11a-135">이름 LRSPowerUserAdminsGroup를 사용 하 여 Active Directory 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="df11a-136">그룹 범위가 전역 및 그룹 유형으로 보안으로 지정 된 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="df11a-137">SIP 사용이 그룹에 추가 된 사용자는 비즈니스용 Skype의 대량 관리를 포함 하 여 모든 관리 포털 기능을 사용할 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="df11a-138">LRSFullAccessAdminGroup를 LRSSupportAdminGroup의 구성원으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup 속성 구성원 페이지](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="df11a-140">이름 LRSSupport를 사용 하 여 SIP 활성화 된 Active Directory 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="df11a-141">이 사용자를 LRSSupportAdminGroup에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup 속성 구성원 페이지](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="df11a-143">[Visual Studio 2010 sp1 및 Visual Web Developer 2010 SP1 용 ASP.NET MVC 4를](https://go.microsoft.com/fwlink/p/?LinkId=323967)설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="df11a-144">SRS v1 관리 웹 포털 설치</span><span class="sxs-lookup"><span data-stu-id="df11a-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="df11a-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="df11a-145"></span></span>

<span data-ttu-id="df11a-146">비즈니스용 [Skype 서버 2015에 대 한 Microsoft Skype 대화방 시스템 V1 관리 웹 포털](https://www.microsoft.com/en-us/download/details.aspx?id=46906)을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="df11a-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="df11a-147">SRS v1 관리 웹 포털을 설치 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="df11a-148">비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 하 여 신뢰할 수 있는 응용 프로그램 포트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="df11a-149">회의실 포털을 설치 하려면 **MeetingRoomPortalInstaller** 를 다운로드 한 다음 관리자 권한으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="df11a-150">다음 위치에서 web.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="df11a-151">비즈니스용 Files%\Skype Server 2015 \ Web Components\Meeting 채팅방 Portal\Int\Handler\의 프로그램</span><span class="sxs-lookup"><span data-stu-id="df11a-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\</span></span>

4. <span data-ttu-id="df11a-152">Web.config 파일에서 PortalUserName을 2 단계에서 만든 사용자 이름으로 변경 하 고 "[SRS V1 관리 웹 포털에 맞게 환경 구성](room-system-v1-administrative-web-portal.md#Config_Env)" 섹션 (단계에서 권장 되는 이름 LRSApp).</span><span class="sxs-lookup"><span data-stu-id="df11a-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="df11a-153">SRS v1 관리 포털은 신뢰할 수 있는 응용 프로그램 이므로 포털 구성에 암호를 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="df11a-154">이 사용자가 로컬 등록 기관 이외의 다른 등록 기관을 사용 하는 경우 web.config 파일에 다음 줄을 추가 하 여 등록 기관에 대 한 등록자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="df11a-155">사용 된 포트가 5061이 아니면 web.config 파일에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="df11a-156">SRS 관리 웹 포털의 설치 확인</span><span class="sxs-lookup"><span data-stu-id="df11a-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="df11a-157">SRS v1 관리 웹 포털의 설치를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="df11a-158">프런트 엔드 서버에서 다음 URL을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="df11a-159">https://\<fe-서버\>/lrs</span><span class="sxs-lookup"><span data-stu-id="df11a-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="df11a-160">다음 이미지와 같이 오류가 표시 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-160">You should not see any errors, as shown in the following image:</span></span>

     ![Lync Room System 관리 포털 로그인 화면](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="df11a-162">오류가 표시 되지 않으면 토폴로지의 다른 컴퓨터에서 다음 URL에 액세스 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="df11a-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="df11a-163">https://\<fe-서버\>/lrs</span><span class="sxs-lookup"><span data-stu-id="df11a-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="df11a-164">페이지에 액세스 하려면 "[자동 클라이언트 로그인에 필요한 Dns 레코드](https://go.microsoft.com/fwlink/p/?LinkId=318056)"에 설명 된 대로 DNS 레코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="df11a-165">SRS 관리 웹 포털 사용</span><span class="sxs-lookup"><span data-stu-id="df11a-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="df11a-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="df11a-166"></span></span>

<span data-ttu-id="df11a-167">서버에 SRS를 배포한 후에는 브라우저에서 SRS v1 관리 웹 포털에 로그인 하 여 모든 SRS 대화방의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="df11a-168">서명하세요</span><span class="sxs-lookup"><span data-stu-id="df11a-168">Sign in</span></span>

1. <span data-ttu-id="df11a-169">다음 URL을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-169">Browse to the following URL:</span></span>

    <span data-ttu-id="df11a-170">https://\<fe-서버\>/lrs</span><span class="sxs-lookup"><span data-stu-id="df11a-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="df11a-171">LRSSupport 계정 또는 LRSSupportAdminGroup 보안 그룹에 추가 된 계정에 대 한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Lync Room System 관리 포털 로그인 화면](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="df11a-173">SRS 관리 웹 포털 요약 페이지</span><span class="sxs-lookup"><span data-stu-id="df11a-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="df11a-174">요약 페이지는 서버에 배포 된 모든 SRS 채팅방에 대해 다음 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="df11a-175">**태그** 관리자가 채팅방에 제공 하는 사용자 지정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="df11a-176">룸 이름을 클릭 하 여 포털에서 태그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="df11a-177">**상태** 룸의 상태 (채팅방 설정 페이지의 상태 섹션 아래에 표시 되는 룸의 집계 상태에서 파생 됨)</span><span class="sxs-lookup"><span data-stu-id="df11a-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="df11a-178">**다음 모임** 다음 모임이 예약 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="df11a-179">**SRS 버전, 제조업체, 모델** 이러한 값은 SRS에서 미리 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="df11a-180">이 필드는 제조업체에 따라 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="df11a-181">**마지막 새로 고침** 웹 페이지를 마지막으로 새로 고친 시간을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync Room System 관리 포털 요약 보기](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="df11a-183">LRSPowerUserAdminsGroup 보안 그룹의 일부인 경우 일괄 관리 메뉴만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="df11a-184">SRS 방 정보</span><span class="sxs-lookup"><span data-stu-id="df11a-184">SRS Room Information</span></span>

<span data-ttu-id="df11a-185">포털의 채팅방 정보 섹션을 통해 개별 SRS 대화방을 보고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="df11a-186">여기에는 네 가지 섹션 (설정, 세부 정보, 기록, 상태)이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="df11a-187">설정</span><span class="sxs-lookup"><span data-stu-id="df11a-187">Settings</span></span>

<span data-ttu-id="df11a-188">설정 섹션에서 회의실에 대 한 암호, 방 태그 및 기본 볼륨 수준을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="df11a-189">이러한 설정을 구성 하는 경우에는 SRS 콘솔을 다시 시작한 후에만 변경 내용이 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="df11a-190">릴리스 15.12 이상을 사용 하는 SRS 장치용 시스템 업데이트 설정만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Lync Room System 관리 포털 채팅방 설정](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="df11a-192">세부적인</span><span class="sxs-lookup"><span data-stu-id="df11a-192">Details</span></span>

<span data-ttu-id="df11a-193">세부 정보 섹션은 다음을 포함 하 여 SRS 룸의 설정에 대 한 읽기 전용 요약을 제공 합니다 (예: 마지막 새로 고침 시간). 다음 모임 마지막 업데이트, 유지 관리 및 보정 기본 스피커, 마이크 및 벨소리 설정 7.0 SIP URI, 각 화면에 대 한 화면 수 및 세부 정보 상태 및 활동.</span><span class="sxs-lookup"><span data-stu-id="df11a-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync Room System 관리 포털 세부 정보 보기](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="df11a-195">해결사</span><span class="sxs-lookup"><span data-stu-id="df11a-195">Troubleshooting</span></span>

<span data-ttu-id="df11a-196">문제 해결 섹션을 사용 하 여 로그를 원격으로 수집 하 고 지정 된 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="df11a-197">SRS 콘솔 (SRS 사용자 인터페이스)을 다시 시작 하거나 전체 시스템을 다시 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="df11a-198">로그를 수집 하려면 지정 된 형식으로 폴더 경로를 제공 하 고 해당 폴더에 SRS 컴퓨터 계정에 대 한 쓰기 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="df11a-199">로그 크기가 너무 크면 로그 수집을 완료 하는 데 최대 5 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="df11a-200">페이지를 새로 고치면 최신 상태가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="df11a-201">체력과</span><span class="sxs-lookup"><span data-stu-id="df11a-201">Health</span></span>

<span data-ttu-id="df11a-202">상태 섹션에는 비즈니스용 Skype 서버 연결, 오디오 장치, 비디오 장치, 복구 상태 및 화면 장치의 상태가 시각적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System 관리 포털 채팅방 상태](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="df11a-204">관리 웹 포털에 대 한 추가 참고 사항</span><span class="sxs-lookup"><span data-stu-id="df11a-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="df11a-205">설정 변경 사항은 SRS 시스템을 다시 시작한 후에만 적용 됩니다. LRSApp 계정 암호가 만료 되는 경우에는 채팅방의 상태를 볼 수 없게 됩니다 >.</span><span class="sxs-lookup"><span data-stu-id="df11a-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="df11a-206">LRSAppuser 계정 암호가 만료 되지 않도록 구성 하거나, 만료가 가까운 경우 암호를 업데이트 해야 합니다. > SRS 관리 웹 포털은 온-프레미스 배포에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="df11a-207">대량 관리</span><span class="sxs-lookup"><span data-stu-id="df11a-207">Bulk management</span></span>

<span data-ttu-id="df11a-208">SRS의 대규모 관리는 고급 IT 관리자를 위해 디자인 된 기능으로, 자신의 워크플로를 단순화 하 고, 대량으로 여러 채팅방을 원격으로 관리할 수 있는 시간을 절약 하는 편리한 도구를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="df11a-209">이 기능을 보려면 사용자를 특수 보안 그룹인 **LRSPowerUserAdminsGroup**의 구성원으로 구축 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="df11a-210">일괄 관리를 위해 선택할 수 있는 SRS의 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="df11a-211">그러나 일괄 관리 작업을 한 번에 하나만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="df11a-212">대량 관리 작업을 수행 하려면 모니터링할 방을 선택 하 고 일괄 관리 메뉴를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="df11a-213">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="df11a-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="df11a-214">관리 웹 포털에 로그인 할 수 없는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="df11a-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="df11a-215">을 열면 https://localhost/lrs로그인 페이지가 표시 되지만 자격 증명을 입력할 때에는 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="df11a-216">이 경우 열려 https://FQDNofFEserver/SRS 있어야 관리 웹 포털에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="df11a-217">관리 웹 포털에 SRS v1이 표시 되지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="df11a-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="df11a-218">배포에 SRS 계정이 있으며 SRS 관리 웹 포털 배포 권장 사항에 따라 생성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="df11a-219">비즈니스용 Skype 서버에서 CsMeetingRoom, Enable이 아닌 사용자를 사용 하 여 SRS 계정이 구축 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="df11a-220">SRS 계정을 만든 경우 관리 웹 포털에서 계정을 볼 수 없는 경우 **MeetingPortal** 구성 요소가 선택 된 비즈니스용 Skype 서버 로깅 도구를 사용 하 여 서버 로그를 수집 하 고이를 SRS 지원 연락처로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="df11a-221">SRS 계정을 만든 경우 관리 웹 포털에서 계정을 볼 수 없는 경우 Fiddler를 사용 하 여 클라이언트 로그를 수집 하 고 브라우저 개발 도구에서 콘솔 로그를 복사한 다음 SRS 지원 연락처로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="df11a-222">Web.config에서 추적 수준 값을 수정 하 여 자세한 로그를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="df11a-223">관리 웹 포털에서 SRS의 상태를 볼 수 없는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="df11a-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="df11a-224">LRSApp 사용자 계정이 SIP를 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="df11a-225">문제가 지속 되는 경우 D:\Tracing\LRSAdminLogs\, 에서 srs 시스템의 **추적** 파일을 수집한 다음 srs 지원 연락처로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="df11a-226">관리 웹 포털에서 SRS에 대 한 대량 관리 메뉴를 볼 수 없는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="df11a-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="df11a-227">LRSApp 사용자 계정이 SIP를 사용 하도록 설정 되어 있고 LRSPowerUserAdminsGroup 보안 그룹에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df11a-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="df11a-228">SRS v1 관리 웹 포털에서 Microsoft 팀 대화방을 사용 합니까?</span><span class="sxs-lookup"><span data-stu-id="df11a-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="df11a-229">아니요.</span><span class="sxs-lookup"><span data-stu-id="df11a-229">No.</span></span>


