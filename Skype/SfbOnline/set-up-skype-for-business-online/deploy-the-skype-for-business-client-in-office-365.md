---
title: Office 365에서 비즈니스용 Skype 클라이언트 배포
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '중소 규모의 대규모 조직에서 비즈니스용 Skype를 계획 하 고 배포 하 고 사용자가 사용할 수 있도록 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 052cc4cb8aa1242628e0f57a57a3fe5532be3d71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706503"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a><span data-ttu-id="c9cf2-103">Office 365에서 비즈니스용 Skype 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="c9cf2-103">Deploy the Skype for Business client in Office 365</span></span>

<span data-ttu-id="c9cf2-104">이 문서에서는 **[관리자](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 가 비즈니스용 Skype 앱을 조직의 사용자에 게 배포할 수 있는 방법에 대 한 옵션에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-104">This article explains options for how you, the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, can deploy the Skype for Business app to the people in your organization.</span></span>
  
<span data-ttu-id="c9cf2-105">비즈니스용 Skype를 사용자에 게 배포 하기 전에 비즈니스용 [Skype Online 설정](set-up-skype-for-business-online.md)문서에서 1-3 단계를 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-105">Before you deploy Skype for Business to your users, make sure you've done steps 1-3 in the article [Set up Skype for Business Online](set-up-skype-for-business-online.md).</span></span> <span data-ttu-id="c9cf2-106">이렇게 하면 비즈니스용 Skype가 도메인에 설정 되 고, 모든 사용자는 자신의 라이선스를 보유 하 고 있으며, 메신저를 구성 하 고 [비즈니스용 Skype Online에서 조직의 현재 상태를 구성할](configure-presence-in-skype-for-business-online.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-106">This way, Skype for Business will be set up with your domain, everyone will have their licenses, and you will have configured IM and [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md) for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9cf2-107">사용자가 비즈니스용 Skype 앱을 설치 하려면 해당 PC 또는 장치에서 로컬 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-107">For users to install the Skype for Business app, they need to be local admins on their PC or device.</span></span> <span data-ttu-id="c9cf2-108">또는 PC 또는 장치에 앱을 설치할 수 있는 로컬 그룹의 일부일 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-108">Or they will need to be part of a local group that can install apps on their PC or devices.</span></span> <span data-ttu-id="c9cf2-109">사용자가 디바이스에 소프트웨어를 설치할 수 없는 경우 비즈니스용 Skype 앱을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-109">If your users aren't allowed to install software on their devices, you'll need to install the Skype for Business app for them.</span></span> 
  
## <a name="for-most-small-and-medium-sized-businesses"></a><span data-ttu-id="c9cf2-110">중소 규모 기업</span><span class="sxs-lookup"><span data-stu-id="c9cf2-110">For most small and medium-sized businesses</span></span>

 <span data-ttu-id="c9cf2-111">단계별 **설치 지침:** 중소 규모의 비즈니스가 있는 경우, 사용자에 게 자신의 PC에 비즈니스용 Skype 앱을 설치 하도록 요청 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-111">**Step-by-step installation instructions:** If you have a small or medium-sized business, we recommend that you simply ask your users to install the Skype for Business app on their PC.</span></span> <span data-ttu-id="c9cf2-112">이 지침을 가리키면 [비즈니스용 Skype를 설치](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-112">Point them to these instructions: [Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb).</span></span> <span data-ttu-id="c9cf2-113">Mac을 사용 하는 경우 [mac 용 Lync 2011 For Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)를 가리키도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-113">If they are using Macs, point them to [Set up Lync for Mac 2011 for Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88).</span></span> <span data-ttu-id="c9cf2-114">비즈니스용 Skype 앱은 나머지 Office 앱과 별도로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-114">The Skype for Business app is installed separately from the rest of the Office apps.</span></span>
  
 <span data-ttu-id="c9cf2-115">**Office 365 ProPlus 고객:** 앱이 E3 계획과 같은 Office 365 ProPlus를 포함 하는 Office 365 계획을 사용 하는 경우 비즈니스용 Skype 앱은 사용자가 Word, Excel, PowerPoint 등을 다운로드 하 고 설치 하는 동시에 설치 됩니다. 이는 또한 모든 Office를 제거 하지 않는 한 비즈니스용 Skype를 제거할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-115">**Office 365 ProPlus customers:** If your business is using an Office 365 plan that includes Office 365 ProPlus, such as the E3 plan, the Skype for Business app is installed at the same time your users download and install Word, Excel, PowerPoint, etc. This also means they can't uninstall Skype for Business unless they uninstall all of Office.</span></span>
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a><span data-ttu-id="c9cf2-116">비즈니스용 Skype를 사용자가 사용할 수 있도록 설정할지 여부 선택</span><span class="sxs-lookup"><span data-stu-id="c9cf2-116">Choose whether to make Skype for Business available to your users</span></span>

<span data-ttu-id="c9cf2-117">[관리자](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) 는 비즈니스용 Skype 앱을 사용자가 사용할 수 있도록 설정할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-117">As the [admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) you can choose whether to make the Skype for Business app available to your users.</span></span>
  
- <span data-ttu-id="c9cf2-118">**회사의 모든 사용자가 소프트웨어를 받을지 여부를 제어 하려면**Microsoft 365 관리 센터에 로그인 하 고 **소프트웨어 설치**로 이동한 다음 사용자에 게 제공 하려는 소프트웨어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-118">**To control whether everyone in your company gets the software**: Sign in to the Microsoft 365 admin center, go to **Install my software**, and then select the software you want to be available for users.</span></span>
    
    ![회사의 사용자가 사용할 수 있도록 설정할 소프트웨어를 선택 합니다.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- <span data-ttu-id="c9cf2-120">**회사의 특정 사용자가 소프트웨어를 받을 수 있는지 제어 하려면**Microsoft 365 관리 센터에 로그인 하 여 **사용자** > **활성 사용자**로 이동 하 고 소프트웨어에 대 한 액세스 권한을 부여할 사용자를 선택한 다음 **제품 라이선스** 옆에 있는 **편집** 을 클릭 하 고 라이선스를 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-120">**To control whether specific people in your company get the software**: Sign in to the Microsoft 365 admin center, go to **Users** > **Active users**, select the person who you want to give access to the software, and then click **Edit** next to **Product licenses** and turn the license on or off.</span></span>
    
    ![사용자가 액세스 하는 데 사용할 소프트웨어를 선택 합니다.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> <span data-ttu-id="c9cf2-122">조직의 사용자에 게 할당 된 계획을 확인 해야 하는 경우 **사용자** > **활성 사용자**> Microsoft 365 관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-122">If you need to see what plans are assigned to people in your organization, sign in to the Microsoft 365 admin center > **Users** > **Active users**.</span></span> <span data-ttu-id="c9cf2-123">목록에서 사용자를 선택 하 고 **제품 라이선스**를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-123">Select the person from the list then look under **Product licenses**.</span></span> <span data-ttu-id="c9cf2-124">클래식 관리 센터를 사용 하는 경우 **할당 된 라이선스**를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-124">If you are using the classic admin center, look under **Assigned license**.</span></span> 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a><span data-ttu-id="c9cf2-125">수동으로 비즈니스용 Skype를 사용자에 게 배포</span><span class="sxs-lookup"><span data-stu-id="c9cf2-125">Manually deploying Skype for Business to your users</span></span>
<span data-ttu-id="c9cf2-126"><a name="bkmk_manual_1"> </a></span><span class="sxs-lookup"><span data-stu-id="c9cf2-126"><a name="bkmk_manual_1"> </a></span></span>

<span data-ttu-id="c9cf2-127">사용자가 인터넷이 아닌 네트워크 위치에서 비즈니스용 Skype 앱을 설치 하도록 하려면 설치 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-127">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files.</span></span> <span data-ttu-id="c9cf2-128">이렇게 하려면 Microsoft 365 관리 센터의 **사용자 소프트웨어 수동 배포** 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-128">To do this go to the **Manually deploy user software** section of the Microsoft 365 admin center.</span></span> <span data-ttu-id="c9cf2-129">그런 다음 **설치** 를 선택 하 고 네트워크 위치에 setup.exe 파일을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-129">You can then select **Install** and save the setup .exe file to a network location.</span></span>
  
<span data-ttu-id="c9cf2-130">다른 옵션은 비즈니스용 Skype Basic 앱을 사용자에 게 다운로드 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-130">Another option is to download the Skype for Business Basic app for your users.</span></span> <span data-ttu-id="c9cf2-131">[Microsoft 비즈니스용 Skype Basic (32 또는 64 비트)](https://www.microsoft.com/download/details.aspx?id=49440)을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-131">You can download [Microsoft Skype for Business Basic (32 or 64 Bit)](https://www.microsoft.com/download/details.aspx?id=49440).</span></span>
  
<span data-ttu-id="c9cf2-132">설치 파일을 다운로드 한 후에는 전체 및 기본 비즈니스용 Skype 앱에 대해 사용자가 설치 프로그램을 실행 하 여 컴퓨터에 앱을 설치할 수 있도록 네트워크 경로를 수동으로 전송 해야 합니다 (예: 전자 메일).</span><span class="sxs-lookup"><span data-stu-id="c9cf2-132">For both the full and basic Skype for Business apps, after you have downloaded the setup files, you will need to manually send (for example, in email) the network path to the users so they can run the setup program to install the app on their computer.</span></span>
  
<span data-ttu-id="c9cf2-133">이러한 다운로드를 사용 하 여 기존 소프트웨어 배포 도구 및 프로세스를 사용 하 여 비즈니스용 Skype 앱을 사용자에 게 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-133">You can also use these downloads to deploy the Skype for Business app to your users by using your existing software deployment tools and processes.</span></span>
  
## <a name="for-larger-and-enterprise-organizations"></a><span data-ttu-id="c9cf2-134">대규모 및 엔터프라이즈 조직의 경우</span><span class="sxs-lookup"><span data-stu-id="c9cf2-134">For larger and enterprise organizations</span></span>

> [!NOTE]
> <span data-ttu-id="c9cf2-135">이 섹션은 Office 365 계획을 통해 제공 되는 비즈니스용 Skype 앱에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-135">This section only applies to the Skype for Business app available through Office 365 plans.</span></span> <span data-ttu-id="c9cf2-136">조직에서 Windows Installer 기반 비즈니스용 Skype 앱의 볼륨 라이선스 버전을 사용 하는 경우 비즈니스용 [Skype 서버에서 windows 클라이언트 설치 사용자 지정](https://technet.microsoft.com/library/jj204934.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-136">If your organization is using a volume licensed version of the Skype for Business app, which is Windows Installer-based (MSI), see [Customize Windows client installation in Skype for Business Server](https://technet.microsoft.com/library/jj204934.aspx).</span></span>
  
<span data-ttu-id="c9cf2-137">여러 기업 또는 대규모 조직에서는 사용자가 자신의 컴퓨터에 소프트웨어를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-137">In many enterprises or large organizations, users aren't allowed to install software on their computers.</span></span> <span data-ttu-id="c9cf2-138">대신 IT 부서가 사용자의 컴퓨터에 필요한 소프트웨어를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-138">Instead, the IT departments deploy the necessary software to the users' computers.</span></span> <span data-ttu-id="c9cf2-139">또한 IT 부서는 조직에서 사용 하는 인터넷 또는 네트워크 대역폭의 양을 제어 하 고 인터넷 이나 회사 네트워크를 통해 네트워크 상에 서 가까운 위치에서 소프트웨어를 설치 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-139">IT departments also might want to control the amount of Internet or network bandwidth used in their organization, so they want to install software from a nearby location on their network instead of from across the Internet or across the corporate network.</span></span>
  
<span data-ttu-id="c9cf2-140">Office 365를 사용 하면 비즈니스용 Skype 앱을 배포 하기 위한 여러 옵션을 사용할 수 있습니다 (설치 위치를 제어 하려는 경우).</span><span class="sxs-lookup"><span data-stu-id="c9cf2-140">With Office 365, you have several options for deploying the Skype for Business app if you want to control where it's installed from.</span></span> <span data-ttu-id="c9cf2-141">이러한 옵션에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-141">Some of those options include the following:</span></span>
  
- <span data-ttu-id="c9cf2-142">비즈니스용 [skype를 사용자에 게 수동으로 배포 하는 방법](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)에 설명 된 바와 같이, Microsoft 365 관리 센터에서 로컬 네트워크에 비즈니스용 skype 앱을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-142">Download the Skype for Business app to your local network from the Microsoft 365 admin center, as described in [Manually deploying Skype for Business to your users](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span></span>
    
- <span data-ttu-id="c9cf2-143">Office **[배포 도구](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 를 사용 하 여 Office 365 ProPlus 또는 비즈니스용 Skype 앱을 로컬 네트워크에 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-143">Use the **[Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** to download either Office 365 ProPlus or the Skype for Business app to your local network.</span></span> <span data-ttu-id="c9cf2-144">그런 다음 Office 배포 도구를 사용 하 여 앱을 사용자에 게 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-144">Then, use the Office Deployment Tool to deploy the app to your users.</span></span> <span data-ttu-id="c9cf2-145">Office 배포 도구를 사용 하면 언어 및 버전 (32 비트 또는 64 비트)과 같은 배포의 특정 측면을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-145">The Office Deployment Tool gives you the ability to control certain aspects of the deployment, such as languages and version (32-bit or 64-bit).</span></span>
    
- <span data-ttu-id="c9cf2-146">Microsoft Endpoint Configuration Manager와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용 하 여 Office 365 ProPlus 또는 비즈니스용 Skype 앱을 사용자에 게 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-146">Use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy Office 365 ProPlus or the Skype for Business app to your users.</span></span> <span data-ttu-id="c9cf2-147">[Office 배포 도구](https://go.microsoft.com/fwlink/p/?LinkID=626065) 또는 Microsoft 365 관리 센터에서 다운로드 한 소프트웨어를 사용 하 여 기존 도구 및 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-147">You can use your existing tools and processes with the [Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) or with the software that you've downloaded from the Microsoft 365 admin center.</span></span>
    
### <a name="more-info-on-using-the-office-deployment-tool"></a><span data-ttu-id="c9cf2-148">Office 배포 도구 사용에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c9cf2-148">More info on using the Office Deployment Tool</span></span>

<span data-ttu-id="c9cf2-149">Office 배포 도구 다운로드에 대 한 자세한 내용과 비즈니스용 Skype 앱 및 기타 Office 365 클라이언트 앱을 설치 하는 방법에 대 한 자세한 내용은 [office 365의 소프트웨어 다운로드 설정 관리](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-149">For details on downloading the Office Deployment Tool and more information on installing the Skype for Business app and other Office 365 client apps, see [Manage software download settings in Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span></span>
  
<span data-ttu-id="c9cf2-150">다음은 Office 배포 도구를 사용 하 여 앱을 배포 하는 데 관련 된 단계를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-150">Here's an overview of the steps involved in using the Office Deployment Tool to deploy an app:</span></span>
  
1. <span data-ttu-id="c9cf2-151">Microsoft 다운로드 센터에서 **[최신 Office 배포 도구를 다운로드](https://www.microsoft.com/download/details.aspx?id=49117)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-151">**[Download the newest Office Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117)** from the Microsoft Download Center.</span></span>
    
2. <span data-ttu-id="c9cf2-152">버전 (32 비트 또는 64 비트), 설치 언어 등의 원하는 클라이언트 앱 설정이 있는 Office 배포 도구에서 사용할 구성 .xml 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-152">Create the configuration.xml file to be used with the Office Deployment Tool that has the client app settings you want, such as setting the version (32-bit or 64-bit), the installation language, etc.</span></span>
    
3. <span data-ttu-id="c9cf2-153">Office 배포 도구 및 구성 .xml 파일을 사용 하 여 Office CDN (콘텐츠 배달 네트워크)에서 로컬 또는 내부 네트워크에 설정 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-153">Use the Office Deployment Tool and the configuration.xml file to download the setup files to your local or internal network from the Office Content Delivery Network (CDN).</span></span>
    
4. <span data-ttu-id="c9cf2-154">Office 배포 도구 및 .xml을 사용 하 여 비즈니스용 Skype 앱을 비롯 한 Office 클라이언트 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-154">Use Office Deployment Tool and the configuration.xml to install the Office client apps, including the Skype for Business app.</span></span>
    
<span data-ttu-id="c9cf2-155">Office 배포 도구 및 구성 .xml 파일을 사용 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-155">For details on using the Office Deployment Tool and configuration.xml file, see the following articles:</span></span>
  
- [<span data-ttu-id="c9cf2-156">Office 배포 도구 개요</span><span class="sxs-lookup"><span data-stu-id="c9cf2-156">Office Deployment Tool overview</span></span>](https://technet.microsoft.com/library/jj219422.aspx)
    
- [<span data-ttu-id="c9cf2-157">구성 xml 설정</span><span class="sxs-lookup"><span data-stu-id="c9cf2-157">Configuration.xml settings</span></span>](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="c9cf2-158">Microsoft 끝점 구성 관리자 사용에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c9cf2-158">More info on using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="c9cf2-159">Microsoft Endpoint Configuration Manager와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용 하 여 비즈니스용 Skype 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-159">You can use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy the Skype for Business app.</span></span> <span data-ttu-id="c9cf2-160">Microsoft 365 관리 센터에서 다운로드 하는 소프트웨어 또는 Office 배포 도구를 사용 하 여 이러한 도구 및 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-160">You can use these tools and processes with either the software that you download from the Microsoft 365 admin center or with the Office Deployment Tool.</span></span>
  
<span data-ttu-id="c9cf2-161">Configuration Manager를 사용 하 여 소프트웨어를 배포 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-161">For more information about using Configuration Manager to deploy software, see the following articles:</span></span>
  
- [<span data-ttu-id="c9cf2-162">Configuration Manager에서 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="c9cf2-162">Create applications in Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [<span data-ttu-id="c9cf2-163">Configuration Manager를 사용 하 여 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="c9cf2-163">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
<span data-ttu-id="c9cf2-164">Office 365 ProPlus 배포의 일부로 비즈니스용 Skype 앱을 배포 하는 경우 [구성 관리자를 사용 하 여 Office 365 ProPlus 관리](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-164">If you're deploying the Skype for Business app as part of deploying Office 365 ProPlus, see [Manage Office 365 ProPlus with Configuration Manager](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates).</span></span>
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a><span data-ttu-id="c9cf2-165">비즈니스용 Skype 앱 업데이트 계획</span><span class="sxs-lookup"><span data-stu-id="c9cf2-165">Planning for updates to the Skype for Business app</span></span>

<span data-ttu-id="c9cf2-166">비즈니스용 skype 앱을 배포 하는 과정의 일환으로 비즈니스용 Skype가 설치 된 후 업데이트를 받는 방법을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-166">As part of deploying the Skype for Business app, you need to consider how you want to get updates after Skype for Business is installed.</span></span> <span data-ttu-id="c9cf2-167">이러한 업데이트에는 안정성 또는 성능 개선을 제공 하는 업데이트와 같은 새로운 기능, 보안 업데이트 또는 비보안 업데이트 등이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-167">These updates can include new features, security updates, or non-security updates, such as updates that provide stability or performance improvements.</span></span> <span data-ttu-id="c9cf2-168">고려해 야 할 두 가지 주요 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-168">The two primary things you need to consider are :</span></span>
  
- <span data-ttu-id="c9cf2-169">업데이트를 받을 위치</span><span class="sxs-lookup"><span data-stu-id="c9cf2-169">Where do you want to get updates from</span></span>
    
- <span data-ttu-id="c9cf2-170">기능 업데이트를 얼마나 자주 받을 지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-170">How often do you want to get feature updates</span></span>
    
<span data-ttu-id="c9cf2-171">업데이트를 받을 위치 및 기능 업데이트를 받을 빈도를 제어할 수 있지만, 어떤 경우에는 어떤 보안 업데이트나 업데이트를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-171">While you can control where you get updates from and how often you get feature updates, you can't choose which specific security updates or non-security updates you get.</span></span>
  
 <span data-ttu-id="c9cf2-172">**업데이트를 받을 위치**</span><span class="sxs-lookup"><span data-stu-id="c9cf2-172">**Where to get updates from**</span></span>
  
<span data-ttu-id="c9cf2-173">기본적으로 비즈니스용 Skype 앱이 설치 된 후에는 Microsoft에서 제공 되는 업데이트가 인터넷에서 자동으로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-173">By default, after the Skype for Business app is installed, updates will be automatically downloaded from the Internet when they are available from Microsoft.</span></span> <span data-ttu-id="c9cf2-174">업데이트가 발생 하는 시기 또는 업데이트가 설치 되는 위치를 보다 효율적으로 제어 하려면 Office 배포 도구 또는 그룹 정책을 사용 하 여 해당 구성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-174">If you want more control over when updates occur or where the updates are installed from, you can use the Office Deployment Tool or Group Policy to configure that.</span></span>
  
<span data-ttu-id="c9cf2-175">예를 들어 조직 전체에 배포 하기 전에 많은 조직이 사용자 그룹을 사용 하 여 업데이트를 테스트 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-175">For example, many organizations want to test updates with a group of users before deploying them throughout the organization.</span></span> <span data-ttu-id="c9cf2-176">Office 배포 도구 또는 그룹 정책을 사용 하 여 비즈니스용 Skype 앱을 구성 하 여 인터넷에서 자동이 아닌 네트워크의 특정 위치에서 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-176">You can do this by using the Office Deployment Tool or Group Policy to configure the Skype for Business app to get updates from a specific location on your network, instead of automatically from the Internet.</span></span> <span data-ttu-id="c9cf2-177">그런 다음 Office 배포 도구를 사용 하 여 매달 업데이트를 로컬 네트워크에 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-177">Then, you can use the Office Deployment Tool to download the updates every month to your local network.</span></span>
  
<span data-ttu-id="c9cf2-178">Office 365 소프트웨어에 대 한 업데이트가 작동 하는 방식에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-178">For more information about how updates work for Office 365 software, see these articles:</span></span>
  
- [<span data-ttu-id="c9cf2-179">Office 365 ProPlus의 업데이트 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="c9cf2-179">Overview of the update process for Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761709.aspx)
    
- [<span data-ttu-id="c9cf2-180">Office 365 ProPlus에 대 한 업데이트를 관리 하는 방법 선택</span><span class="sxs-lookup"><span data-stu-id="c9cf2-180">Choose how to manage updates to Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761707.aspx)
    
- [<span data-ttu-id="c9cf2-181">Office 365 ProPlus에 대 한 업데이트 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c9cf2-181">Configure update settings for Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761708.aspx)
    
  <span data-ttu-id="c9cf2-182">**기능 업데이트를 얻는 빈도**</span><span class="sxs-lookup"><span data-stu-id="c9cf2-182">**How often to get feature updates**</span></span>
  
<span data-ttu-id="c9cf2-183">업데이트를 받을 수 있는 위치 외에도 비즈니스용 Skype 클라이언트에 대 한 새로운 기능을 받을 빈도를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-183">In addition to where you get updates from, you can also control how often you get new features for the Skype for Business client.</span></span> <span data-ttu-id="c9cf2-184">두 가지 선택 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-184">The two choices are the following:</span></span>
  
- <span data-ttu-id="c9cf2-185">새로운 기능이 있는 경우 매달 기능 업데이트 받기</span><span class="sxs-lookup"><span data-stu-id="c9cf2-185">Get feature updates every month, if there are new features</span></span>
    
- <span data-ttu-id="c9cf2-186">6 개월 마다 기능을 업데이트 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-186">Get features updates every six months</span></span>
    
<span data-ttu-id="c9cf2-187">일부 조직의 경우 새 기능을 테스트 하는 데 시간이 필요 하므로, 매월 1 년이 아닌 두 번의 기능 업데이트를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-187">For some organizations, they want time to test new features, so they want to get feature updates only twice a year instead of every month.</span></span>
  
<span data-ttu-id="c9cf2-188">Office 배포 도구 또는 그룹 정책을 사용 하 여 업데이트 채널을 구성 하 여 기능 업데이트를 받을 빈도를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-188">You can control how often you get feature updates by using the Office Deployment Tool or Group Policy to configure the update channel.</span></span> <span data-ttu-id="c9cf2-189">월 단위 채널은 월간 업데이트 기능을 제공 하는 반면, 반기 채널은 6 개월 마다 기능을 업데이트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-189">The Monthly Channel gives you feature updates monthly (approximately), while the Semi-Annual Channel gives you feature updates every six months.</span></span> <span data-ttu-id="c9cf2-190">채널에 대 한 자세한 내용은 [Office 365 ProPlus의 업데이트 채널 개요](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9cf2-190">For more information about channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c9cf2-191">관련 주제</span><span class="sxs-lookup"><span data-stu-id="c9cf2-191">Related topics</span></span>

[<span data-ttu-id="c9cf2-192">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="c9cf2-192">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="c9cf2-193">비즈니스용 Skype 및 Microsoft 팀 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="c9cf2-193">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
