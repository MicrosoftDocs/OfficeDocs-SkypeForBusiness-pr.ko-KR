---
title: 환경 준비
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 모든 기능을 활용할 수 있도록 Microsoft Teams 룸 인프라를 준비하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117426"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="e8321-103">작업 환경 준비</span><span class="sxs-lookup"><span data-stu-id="e8321-103">Prepare your environment</span></span>

<span data-ttu-id="e8321-104">이 섹션에는 환경을 준비하는 데 필요한 단계에 대한 개요가 포함되어 있으므로 모든 기능을 사용할 수 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="e8321-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="e8321-105">각 콘솔에 대한 디바이스 Microsoft Teams 룸 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="e8321-106">자세한 [내용은 Microsoft Teams 룸](rooms-deploy.md) 배포를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="e8321-107">디바이스에서 사용할 네트워크/인터넷 연결이 작동하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="e8321-108">DHCP를 사용하여 IP 주소를 받을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="e8321-109">(Microsoft Teams 룸 시작 시 정적 IP 주소로 구성할 수는 없지만, 이후 디바이스 또는 업스트림 스위치 또는 라우터에서 디바이스에 대한 정적 IP 주소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="e8321-110">미디어에 대한 일반 포트를 여는 것 외에도 이러한 포트가 열려 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="e8321-111">HTTPS: 443</span><span class="sxs-lookup"><span data-stu-id="e8321-111">HTTPS: 443</span></span>
   - <span data-ttu-id="e8321-112">HTTP: 80</span><span class="sxs-lookup"><span data-stu-id="e8321-112">HTTP: 80</span></span>

   <span data-ttu-id="e8321-113">네트워크가 프록시를 통해 실행되는 경우 프록시 주소 또는 스크립트 정보도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="e8321-114">Microsoft Teams 룸 작업을 방해할 수 있는 프록시 인증을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="e8321-115">프로덕션에 Microsoft Teams 룸 프록시 인증에서 제외된지 확인</span><span class="sxs-lookup"><span data-stu-id="e8321-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="e8321-116">환경을 개선하기 위해 Microsoft는 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="e8321-117">Microsoft에서 데이터를 수집하도록 허용하기 위해 다음 사이트를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="e8321-118">원격 분석 클라이언트 엔드포인트: https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="e8321-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="e8321-119">원격 분석 설정 엔드포인트: https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="e8321-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="e8321-120">디바이스 계정 만들기 및 테스트</span><span class="sxs-lookup"><span data-stu-id="e8321-120">Create and test a device account</span></span>

<span data-ttu-id="e8321-121">디바이스 *계정은* Microsoft Teams 룸 클라이언트가 일정과 같은 Exchange 기능에 액세스하고, 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="e8321-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="e8321-122">자세한 [내용은 Microsoft Teams 룸](rooms-deploy.md) 배포를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="e8321-123">네트워크 가용성 확인</span><span class="sxs-lookup"><span data-stu-id="e8321-123">Check network availability</span></span>

<span data-ttu-id="e8321-124">제대로 작동하려면 Microsoft Teams 룸 요구 사항을 충족하는 유선 네트워크에 대한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="e8321-125">Active Directory 또는 Azure AD(Azure Active Directory) 인스턴스 및 Microsoft Exchange 및 비즈니스용 Skype 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="e8321-126">DHCP를 사용하여 IP 주소를 제공할 수 있는 서버에 대한 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="e8321-127">Microsoft Teams 룸 시작 시 정적 IP 주소로 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="e8321-128">HTTP 포트 80 및 443에 대한 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="e8321-129">TCP 및 UDP 포트는 프레미스 비즈니스용 Skype 서버 구현을 위한 서버의 포트 및 프로토콜 요구 사항 또는 Microsoft 365 및 Office 365 URL 및 [IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) 주소 범위에 Microsoft Teams 또는 비즈니스용 Skype 구성합니다. [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)</span><span class="sxs-lookup"><span data-stu-id="e8321-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8321-130">필요한 대역폭을 보장하기 위해 유선 1Gbps 네트워크 연결을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="e8321-131">소프트웨어 업데이트는 Microsoft Teams 룸 자동으로 다운로드 비즈니스용 Microsoft Store됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="e8321-132">룸 [콘솔이](/microsoft-store/prerequisites-microsoft-store-for-business) 저장소 및 자체 업데이트에 액세스할 수 비즈니스용 Microsoft Store 확인을 위해 교육 및 교육에 대한 전제 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-132">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="e8321-133">인증서</span><span class="sxs-lookup"><span data-stu-id="e8321-133">Certificates</span></span>

<span data-ttu-id="e8321-134">사용자 Microsoft Teams 룸 디바이스는 웹 서비스, Exchange, Microsoft Teams 또는 비즈니스용 Skype, 네트워크 사용 및 인증에 대해 인증서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="e8321-135">관련 서버가 공용 인증서를 사용하는 경우( Online 및 일부 On-Premises 배포의 경우) 인증서를 설치하는 데 관리자의 일부에서 추가 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="e8321-136">반면에 인증서 기관이 사설 CA(On-Premises 배포에 일반적)인 경우 디바이스는 CA + CA 체인 인증서가 디바이스에 설치되어 있는 CA를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="e8321-137">도메인에 디바이스를 추가하면 이 작업이 자동으로 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="e8321-138">다른 클라이언트의 경우와 동일한 방식으로 인증서를 Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e8321-139">인증서를 사용하려면 인증서가 Microsoft Teams 룸 비즈니스용 Skype 서버.</span><span class="sxs-lookup"><span data-stu-id="e8321-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="e8321-140">프록시</span><span class="sxs-lookup"><span data-stu-id="e8321-140">Proxy</span></span>

<span data-ttu-id="e8321-141">Microsoft Teams 룸 OS에서 프록시 설정을 상속하도록 Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="e8321-142">다음과 Windows OS에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="e8321-143">Microsoft Teams 룸 UI에서 디바이스의 로컬 관리자 암호에 대한 메시지가 설정 기어 아이콘을 클릭합니다(기본 암호는 **sfb입니다).**</span><span class="sxs-lookup"><span data-stu-id="e8321-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="e8321-144">다음에  설정 탭한 다음 이동 단추를 Windows 탭한 다음 관리자 로그인 단추로 이동 단추를 탭한  다음 관리자 단추를 클릭합니다(컴퓨터가  도메인에 가입된 경우 다른 사용자를 선택한 다음 .\admin을 사용자 이름으로 사용).  </span><span class="sxs-lookup"><span data-stu-id="e8321-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="e8321-145">검색 **Windows** 왼쪽 아래 형식의 regedit(화면을 길게 누르거나 마우스 오른쪽 단추로 클릭하고 관리자 권한으로 실행을 **선택합니다).**</span><span class="sxs-lookup"><span data-stu-id="e8321-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="e8321-146">HKEY_USERS 폴더(컴퓨터 사용자 SID 목록이 표시됩니다)를 클릭하여 루트 폴더가 선택되어 HKEY_USERS 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="e8321-147">파일을 클릭한 다음 **Hive 로드를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="e8321-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="e8321-148">**C:\Users\Skype** 폴더로 찾아 파일 이름 상자 NTUSER.dat를 입력하고 열기 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="e8321-149">새로 로드된 Hive에 대한 키 이름을 묻는 메시지가 표시됩니다. Skype 입력합니다(이제 사용자에 대한 레지스트리 Skype 표시됩니다).</span><span class="sxs-lookup"><span data-stu-id="e8321-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="e8321-150">Skype 키를 열고 HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings 다음 설정을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="e8321-151">ProxyServer가 존재하지 않는 경우 이 키를 문자열로 추가해야 할 수 있습니다. xx.xx.xx.xx:8080을 프록시 서버의 ip/host 및 포트에 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="e8321-152">고객이 PAC 파일을 사용하는 경우 구성은 아래 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="e8321-153">변경이 완료되면 Skype 사용자 키(Skype 루트 폴더)를 강조 표시하고 레지스트리 파일 메뉴에서 Hive 언로드를 선택합니다(확인하라는 메시지가 표시됩니다. **예를 선택합니다).**</span><span class="sxs-lookup"><span data-stu-id="e8321-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="e8321-154">이제 레지스트리 편집기를 닫고 로고프를 검색 상자에 Windows 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="e8321-155">로그인 화면으로 돌아가서 사용자를 Skype **합니다.**</span><span class="sxs-lookup"><span data-stu-id="e8321-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="e8321-156">이전 모든 단계가 성공한 경우 Microsoft Teams 룸 디바이스가 성공적으로 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="e8321-157">FQDNs, 포트 및 IP 주소 범위에 대한 자세한 내용은 네트워크 보안 문서를 참조하여 Microsoft Teams 룸. [](./security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="e8321-157">See the [Network Security](./security.md#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="e8321-158">프로비전 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="e8321-158">Create provisioning packages</span></span>

<span data-ttu-id="e8321-159">프로비전 패키지를 사용하여 Exchange Server, Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8321-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="e8321-160">관리 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="e8321-160">Admin group management</span></span>

<span data-ttu-id="e8321-161">도메인에 가입한 후 그룹 정책 또는 로컬 컴퓨터 관리를 사용하여 도메인의 PC를 사용하는 경우와 마찬가지로 보안 그룹을 로컬 관리자로 Windows 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="e8321-162">보안 그룹의 구성원인 모든 사람은 자격 증명을 입력하고 자격 증명을 잠금 해제할 설정.</span><span class="sxs-lookup"><span data-stu-id="e8321-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8321-163">Microsoft Teams 룸 디바이스가 도메인에 대한 신뢰를 잃는 경우(예: 도메인에 가입된 Microsoft Teams 룸 도메인에서 해당 도메인을 제거한 경우) 디바이스에 인증하고 도메인을 열 수 설정.</span><span class="sxs-lookup"><span data-stu-id="e8321-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="e8321-164">해결은 로컬 관리자 계정으로 로그인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="e8321-165">로컬 계정</span><span class="sxs-lookup"><span data-stu-id="e8321-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="e8321-166">Microsoft Teams 룸 로컬 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="e8321-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="e8321-167">디바이스 계정은 일반적으로 암호를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="e8321-168">암호를 입력할 수 있지만 해당 암호가 만료되면 사용자가 콘솔 애플리케이션에서 잠겨 있을 수 있는 가능성을 포함하여 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="e8321-169">따라서 관리자는 암호를 만료할 수 없는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="e8321-170">"관리자" - 로컬 관리자 계정</span><span class="sxs-lookup"><span data-stu-id="e8321-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="e8321-171">Microsoft Teams 룸 암호는 "sfb"로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="e8321-172">암호는 Windows 설정 파일로 이동하거나 Windows 또는 AutoUnattend.xml 파일로 이동하여 로컬로 변경할 수 있습니다(ADK의 Windows 시스템 이미지 관리자를 사용하여 xml 파일을 \> 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e8321-173">가능한 한 빨리 Microsoft Teams 룸 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="e8321-174">도메인 관리자가 로컬 관리자로 설정되는 그룹 정책을 설정하여 로컬 관리자 암호를 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="e8321-175">로컬 관리자 암호는 설정 중에 선택으로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="e8321-176">컴퓨터 계정</span><span class="sxs-lookup"><span data-stu-id="e8321-176">Machine Account</span></span>

<span data-ttu-id="e8321-177">다른 디바이스와 Windows 마찬가지로 PC 이름 변경에 대해 마우스 **오른쪽 단추로 클릭하여** 컴퓨터 이름을 설정 \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e8321-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="e8321-178">도메인에 가입한 후 컴퓨터의 이름을 변경하려면 컴퓨터의 새 이름 다음에 PowerShell 명령인 **Rename-Computer를** 사용하여 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e8321-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e8321-179">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e8321-179">Related topics</span></span>

[<span data-ttu-id="e8321-180">계획 Microsoft Teams 룸</span><span class="sxs-lookup"><span data-stu-id="e8321-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="e8321-181">Microsoft Teams 룸 요구사항</span><span class="sxs-lookup"><span data-stu-id="e8321-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="e8321-182">Microsoft Teams 룸 배포</span><span class="sxs-lookup"><span data-stu-id="e8321-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="e8321-183">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="e8321-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="e8321-184">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="e8321-184">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="e8321-185">교육 및 교육을 위한 비즈니스용 Microsoft Store 전제</span><span class="sxs-lookup"><span data-stu-id="e8321-185">Prerequisites for Microsoft Store for Business and Education</span></span>](/microsoft-store/prerequisites-microsoft-store-for-business)