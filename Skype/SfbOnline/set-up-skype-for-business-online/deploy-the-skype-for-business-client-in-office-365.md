---
title: Microsoft 365 aor Office 365에서 비즈니스용 Skype 클라이언트 배포
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
description: '소규모, 중소 및 대규모 조직에서 비즈니스용 Skype를 계획하고 배포하고 사용자에게 사용할 수 있도록 하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 7a2ba51a315b77c501735be863f342c1bdb1548f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097294"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a><span data-ttu-id="77440-103">Microsoft 365 또는 Office 365에서 비즈니스용 Skype 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="77440-103">Deploy the Skype for Business client in Microsoft 365 or Office 365</span></span>

<span data-ttu-id="77440-104">이 문서에서는 관리자인 사용자가 **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 조직의 사용자에게 비즈니스용 Skype 앱을 배포하는 방법에 대한 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-104">This article explains options for how you, the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, can deploy the Skype for Business app to the people in your organization.</span></span>
  
<span data-ttu-id="77440-105">비즈니스용 Skype를 사용자에게 배포하기 전에 비즈니스용 Skype Online 설정 문서에서 1-3단계를 [완료해야 합니다.](set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="77440-105">Before you deploy Skype for Business to your users, make sure you've done steps 1-3 in the article [Set up Skype for Business Online](set-up-skype-for-business-online.md).</span></span> <span data-ttu-id="77440-106">이렇게 하면 비즈니스용 Skype가 도메인으로 설정되어 모든 사용자가 라이선스를 가지며, 조직에 대한 [비즈니스용 Skype Online에서](configure-presence-in-skype-for-business-online.md) IM 및 현재 상태 구성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-106">This way, Skype for Business will be set up with your domain, everyone will have their licenses, and you will have configured IM and [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md) for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77440-107">사용자가 비즈니스용 Skype 앱을 설치하려면 PC 또는 디바이스에 로컬 관리자로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-107">For users to install the Skype for Business app, they need to be local admins on their PC or device.</span></span> <span data-ttu-id="77440-108">또는 PC 또는 디바이스에 앱을 설치할 수 있는 로컬 그룹에 참여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-108">Or they will need to be part of a local group that can install apps on their PC or devices.</span></span> <span data-ttu-id="77440-109">사용자가 디바이스에 소프트웨어를 설치할 수 없는 경우 비즈니스용 Skype 앱을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-109">If your users aren't allowed to install software on their devices, you'll need to install the Skype for Business app for them.</span></span> 
  
## <a name="for-most-small-and-medium-sized-businesses"></a><span data-ttu-id="77440-110">대부분의 중소기업의 경우</span><span class="sxs-lookup"><span data-stu-id="77440-110">For most small and medium-sized businesses</span></span>

 <span data-ttu-id="77440-111">**단계별 설치 지침:** 중소기업이 있는 경우 사용자에게 비즈니스용 Skype 앱을 PC에 설치하도록 요청하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-111">**Step-by-step installation instructions:** If you have a small or medium-sized business, we recommend that you simply ask your users to install the Skype for Business app on their PC.</span></span> <span data-ttu-id="77440-112">이러한 지침은 [비즈니스용 Skype 설치 를 지시합니다.](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)</span><span class="sxs-lookup"><span data-stu-id="77440-112">Point them to these instructions: [Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb).</span></span> <span data-ttu-id="77440-113">Mac을 사용하는 경우 Office [365용 Mac 2011용 Lync 설정 을 지적합니다.](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)</span><span class="sxs-lookup"><span data-stu-id="77440-113">If they are using Macs, point them to [Set up Lync for Mac 2011 for Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88).</span></span> <span data-ttu-id="77440-114">비즈니스용 Skype 앱은 나머지 Office 앱과 별도로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="77440-114">The Skype for Business app is installed separately from the rest of the Office apps.</span></span>
  
 <span data-ttu-id="77440-115">엔터프라이즈 고객을 위한 **Microsoft 365 Apps:** 비즈니스에서 엔터프라이즈용 Microsoft 365 Apps(예: E3 요금제)를 포함하는 Office 365 요금제를 사용하는 경우 사용자가 Word, Excel, PowerPoint 등을 다운로드하고 설치하는 동시에 비즈니스용 Skype 앱이 설치됩니다. 또한 Office를 모두 제거하지 않으면 비즈니스용 Skype를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-115">**Microsoft 365 Apps for enterprise customers:** If your business is using an Office 365 plan that includes Microsoft 365 Apps for enterprise, such as the E3 plan, the Skype for Business app is installed at the same time your users download and install Word, Excel, PowerPoint, etc. This also means they can't uninstall Skype for Business unless they uninstall all of Office.</span></span>
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a><span data-ttu-id="77440-116">사용자가 비즈니스용 Skype를 사용할 수 있도록 할지 여부를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="77440-116">Choose whether to make Skype for Business available to your users</span></span>

<span data-ttu-id="77440-117">관리자는 [](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) 사용자가 비즈니스용 Skype 앱을 사용할 수 있도록 할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-117">As the [admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) you can choose whether to make the Skype for Business app available to your users.</span></span>
  
- <span data-ttu-id="77440-118">**회사의** 모든 사용자가 소프트웨어 : Microsoft 365 관리 센터에 로그인하는지 여부를 제어하려면 내 소프트웨어 설치로 이동한 다음 사용자가 사용할 수 있는 소프트웨어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-118">**To control whether everyone in your company gets the software**: Sign in to the Microsoft 365 admin center, go to **Install my software**, and then select the software you want to be available for users.</span></span>
    
    ![회사에 있는 사용자들이 사용할 수 있도록 할 소프트웨어를 선택하십시오.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- <span data-ttu-id="77440-120">**회사의** 특정 사용자가 소프트웨어를 받을지 여부를 제어하려면 Microsoft 365 관리 센터에 로그인하려면 **사용자** 활성 사용자로 이동하여 소프트웨어에 대한 액세스 권한을 부여할 사용자를 선택한 다음 제품 라이선스 옆에 있는 편집을 클릭하고 라이선스를 켜거나 끄면  >  됩니다.  </span><span class="sxs-lookup"><span data-stu-id="77440-120">**To control whether specific people in your company get the software**: Sign in to the Microsoft 365 admin center, go to **Users** > **Active users**, select the person who you want to give access to the software, and then click **Edit** next to **Product licenses** and turn the license on or off.</span></span>
    
    ![사용자가 액세스할 소프트웨어를 선택할 수 있습니다.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> <span data-ttu-id="77440-122">조직의 사용자에게 할당된 계획을 확인해야 하는 경우 Microsoft 365 관리 센터에 로그인하여 사용자 **>**  >  **합니다.**</span><span class="sxs-lookup"><span data-stu-id="77440-122">If you need to see what plans are assigned to people in your organization, sign in to the Microsoft 365 admin center > **Users** > **Active users**.</span></span> <span data-ttu-id="77440-123">목록에서 사람을 선택한 다음 제품 라이선스 **아래를 봐야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77440-123">Select the person from the list then look under **Product licenses**.</span></span> <span data-ttu-id="77440-124">클래식 관리 센터를 사용하는 경우 할당된 라이선스 **를 살펴 봐야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77440-124">If you are using the classic admin center, look under **Assigned license**.</span></span> 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a><span data-ttu-id="77440-125">사용자에게 비즈니스용 Skype를 수동으로 배포</span><span class="sxs-lookup"><span data-stu-id="77440-125">Manually deploying Skype for Business to your users</span></span>
<span data-ttu-id="77440-126"><a name="bkmk_manual_1"> </a></span><span class="sxs-lookup"><span data-stu-id="77440-126"><a name="bkmk_manual_1"> </a></span></span>

<span data-ttu-id="77440-127">사용자가 인터넷 대신 네트워크의 위치에서 비즈니스용 Skype 앱을 설치하려면 설치 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-127">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files.</span></span> <span data-ttu-id="77440-128">이렇게하려면 Microsoft 365 관리 센터의 사용자 소프트웨어 수동으로 배포 섹션으로 이동하세요. </span><span class="sxs-lookup"><span data-stu-id="77440-128">To do this go to the **Manually deploy user software** section of the Microsoft 365 admin center.</span></span> <span data-ttu-id="77440-129">그런 다음 설치를 **선택하고** 설치 .exe 파일을 네트워크 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-129">You can then select **Install** and save the setup .exe file to a network location.</span></span>
  
<span data-ttu-id="77440-130">또 다른 옵션은 사용자의 비즈니스용 Skype 기본 앱을 다운로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="77440-130">Another option is to download the Skype for Business Basic app for your users.</span></span> <span data-ttu-id="77440-131">비즈니스용 [Microsoft Skype 기본(32 또는 64비트)을 다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=49440)</span><span class="sxs-lookup"><span data-stu-id="77440-131">You can download [Microsoft Skype for Business Basic (32 or 64 Bit)](https://www.microsoft.com/download/details.aspx?id=49440).</span></span>
  
<span data-ttu-id="77440-132">전체 및 기본 비즈니스용 Skype 앱의 경우 설정 파일을 다운로드한 후 사용자에게 네트워크 경로를 수동으로 보내서 설치 프로그램을 실행하여 해당 컴퓨터에 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-132">For both the full and basic Skype for Business apps, after you have downloaded the setup files, you will need to manually send (for example, in email) the network path to the users so they can run the setup program to install the app on their computer.</span></span>
  
<span data-ttu-id="77440-133">이러한 다운로드를 사용하여 기존 소프트웨어 배포 도구 및 프로세스를 사용하여 사용자에게 비즈니스용 Skype 앱을 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-133">You can also use these downloads to deploy the Skype for Business app to your users by using your existing software deployment tools and processes.</span></span>
  
## <a name="for-larger-and-enterprise-organizations"></a><span data-ttu-id="77440-134">대규모 및 엔터프라이즈 조직의 경우</span><span class="sxs-lookup"><span data-stu-id="77440-134">For larger and enterprise organizations</span></span>

> [!NOTE]
> <span data-ttu-id="77440-135">이 섹션은 Office 365 요금제에서 사용할 수 있는 비즈니스용 Skype 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77440-135">This section only applies to the Skype for Business app available through Office 365 plans.</span></span> <span data-ttu-id="77440-136">조직에서 MSI(Windows Installer 기반)인 비즈니스용 Skype 앱의 볼륨 사용이 허가된 버전을 사용하는 경우 비즈니스용 Skype Server에서 Windows 클라이언트 설치 사용자 지정을 [참조하세요.](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)</span><span class="sxs-lookup"><span data-stu-id="77440-136">If your organization is using a volume licensed version of the Skype for Business app, which is Windows Installer-based (MSI), see [Customize Windows client installation in Skype for Business Server](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md).</span></span>
  
<span data-ttu-id="77440-137">많은 기업 또는 대규모 조직에서 사용자는 컴퓨터에 소프트웨어를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-137">In many enterprises or large organizations, users aren't allowed to install software on their computers.</span></span> <span data-ttu-id="77440-138">대신 IT 부서는 사용자의 컴퓨터에 필요한 소프트웨어를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-138">Instead, the IT departments deploy the necessary software to the users' computers.</span></span> <span data-ttu-id="77440-139">또한 IT 부서는 조직에서 사용되는 인터넷 또는 네트워크 대역폭의 양을 제어하기를 원할 수 있으므로 인터넷을 가로질러 또는 회사 네트워크를 가로지르는 대신 네트워크의 가까운 위치에서 소프트웨어를 설치하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-139">IT departments also might want to control the amount of Internet or network bandwidth used in their organization, so they want to install software from a nearby location on their network instead of from across the Internet or across the corporate network.</span></span>
  
<span data-ttu-id="77440-140">Office 365에서는 설치 위치를 제어하려는 경우 비즈니스용 Skype 앱을 배포하기 위한 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-140">With Office 365, you have several options for deploying the Skype for Business app if you want to control where it's installed from.</span></span> <span data-ttu-id="77440-141">이러한 옵션 중 일부는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-141">Some of those options include the following:</span></span>
  
- <span data-ttu-id="77440-142">사용자에게 비즈니스용 Skype를 수동으로 배포하는 데 설명된 바와 같이 Microsoft 365 관리 센터에서 비즈니스용 Skype 앱을 로컬 네트워크에 [다운로드합니다.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)</span><span class="sxs-lookup"><span data-stu-id="77440-142">Download the Skype for Business app to your local network from the Microsoft 365 admin center, as described in [Manually deploying Skype for Business to your users](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span></span>
    
- <span data-ttu-id="77440-143">Office **[배포 도구를](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 사용하여 엔터프라이즈용 Microsoft 365 Apps 또는 비즈니스용 Skype 앱을 로컬 네트워크에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-143">Use the **[Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** to download either Microsoft 365 Apps for enterprise or the Skype for Business app to your local network.</span></span> <span data-ttu-id="77440-144">그런 다음 Office 배포 도구를 사용하여 사용자에게 앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-144">Then, use the Office Deployment Tool to deploy the app to your users.</span></span> <span data-ttu-id="77440-145">Office 배포 도구를 사용하면 언어 및 버전(32비트 또는 64비트)과 같은 배포의 특정 측면을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-145">The Office Deployment Tool gives you the ability to control certain aspects of the deployment, such as languages and version (32-bit or 64-bit).</span></span>
    
- <span data-ttu-id="77440-146">Microsoft 엔드포인트 구성 관리자와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용하여 엔터프라이즈용 Microsoft 365 Apps 또는 비즈니스용 Skype 앱을 사용자에게 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-146">Use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy Microsoft 365 Apps for enterprise or the Skype for Business app to your users.</span></span> <span data-ttu-id="77440-147">Office 배포 도구 또는 [Microsoft](https://go.microsoft.com/fwlink/p/?LinkID=626065) 365 관리 센터에서 다운로드한 소프트웨어와 함께 기존 도구 및 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-147">You can use your existing tools and processes with the [Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) or with the software that you've downloaded from the Microsoft 365 admin center.</span></span>
    
### <a name="more-info-on-using-the-office-deployment-tool"></a><span data-ttu-id="77440-148">Office 배포 도구 사용에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="77440-148">More info on using the Office Deployment Tool</span></span>

<span data-ttu-id="77440-149">Office 배포 도구 다운로드에 대한 자세한 내용 및 비즈니스용 Skype 앱 및 기타 Office 365 클라이언트 앱 설치에 대한 자세한 내용은 [Office 365의](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)소프트웨어 다운로드 설정 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77440-149">For details on downloading the Office Deployment Tool and more information on installing the Skype for Business app and other Office 365 client apps, see [Manage software download settings in Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span></span>
  
<span data-ttu-id="77440-150">Office 배포 도구를 사용하여 앱을 배포하는 데 관련된 단계에 대한 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-150">Here's an overview of the steps involved in using the Office Deployment Tool to deploy an app:</span></span>
  
1. <span data-ttu-id="77440-151">Microsoft 다운로드 **[센터에서 최신 Office 배포](https://www.microsoft.com/download/details.aspx?id=49117)** 도구를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-151">**[Download the newest Office Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117)** from the Microsoft Download Center.</span></span>
    
2. <span data-ttu-id="77440-152">configuration.xml 버전 설정(32비트 또는 64비트), 설치 언어 등 원하는 클라이언트 앱 설정이 있는 Office 배포 도구에서 사용할 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="77440-152">Create the configuration.xml file to be used with the Office Deployment Tool that has the client app settings you want, such as setting the version (32-bit or 64-bit), the installation language, etc.</span></span>
    
3. <span data-ttu-id="77440-153">Office 배포 도구 및 configuration.xml 파일을 사용하여 CDN(Office 콘텐츠 배달 네트워크)에서 로컬 또는 내부 네트워크에 설치 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-153">Use the Office Deployment Tool and the configuration.xml file to download the setup files to your local or internal network from the Office Content Delivery Network (CDN).</span></span>
    
4. <span data-ttu-id="77440-154">Office 배포 도구 및 configuration.xml 비즈니스용 Skype 앱을 포함하여 Office 클라이언트 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-154">Use Office Deployment Tool and the configuration.xml to install the Office client apps, including the Skype for Business app.</span></span>
    
<span data-ttu-id="77440-155">Office 배포 도구 및 파일 configuration.xml 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77440-155">For details on using the Office Deployment Tool and configuration.xml file, see the following articles:</span></span>
  
- [<span data-ttu-id="77440-156">Office 배포 도구 개요</span><span class="sxs-lookup"><span data-stu-id="77440-156">Office Deployment Tool overview</span></span>](/deployoffice/overview-office-deployment-tool)
    
- [<span data-ttu-id="77440-157">Configuration.xml 설정</span><span class="sxs-lookup"><span data-stu-id="77440-157">Configuration.xml settings</span></span>](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="77440-158">Microsoft 엔드포인트 구성 관리자 사용에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="77440-158">More info on using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="77440-159">Microsoft 엔드포인트 구성 관리자와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용하여 비즈니스용 Skype 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-159">You can use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy the Skype for Business app.</span></span> <span data-ttu-id="77440-160">Microsoft 365 관리 센터에서 다운로드한 소프트웨어 또는 Office 배포 도구와 함께 이러한 도구 및 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-160">You can use these tools and processes with either the software that you download from the Microsoft 365 admin center or with the Office Deployment Tool.</span></span>
  
<span data-ttu-id="77440-161">Configuration Manager를 사용하여 소프트웨어 배포에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77440-161">For more information about using Configuration Manager to deploy software, see the following articles:</span></span>
  
- [<span data-ttu-id="77440-162">Configuration Manager에서 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="77440-162">Create applications in Configuration Manager</span></span>](/configmgr/apps/deploy-use/create-applications)
    
- [<span data-ttu-id="77440-163">Configuration Manager를 통해 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="77440-163">Deploy applications with Configuration Manager</span></span>](/configmgr/apps/deploy-use/deploy-applications)
    
<span data-ttu-id="77440-164">엔터프라이즈용 Microsoft 365 Apps 배포의 일환으로 비즈니스용 Skype 앱을 배포하는 경우 Configuration Manager를 사용하여 [엔터프라이즈용 Microsoft 365 앱 관리를 참조하세요.](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)</span><span class="sxs-lookup"><span data-stu-id="77440-164">If you're deploying the Skype for Business app as part of deploying Microsoft 365 Apps for enterprise, see [Manage Microsoft 365 Apps for enterprise with Configuration Manager](/configmgr/sum/deploy-use/manage-office-365-proplus-updates).</span></span>
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a><span data-ttu-id="77440-165">비즈니스용 Skype 앱 업데이트 계획</span><span class="sxs-lookup"><span data-stu-id="77440-165">Planning for updates to the Skype for Business app</span></span>

<span data-ttu-id="77440-166">비즈니스용 Skype 앱을 배포하는 일환으로 비즈니스용 Skype를 설치한 후 업데이트를 받을 방법을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-166">As part of deploying the Skype for Business app, you need to consider how you want to get updates after Skype for Business is installed.</span></span> <span data-ttu-id="77440-167">이러한 업데이트에는 안정성 또는 성능 개선을 제공하는 업데이트와 같은 새로운 기능, 보안 업데이트 또는 비보안 업데이트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="77440-167">These updates can include new features, security updates, or non-security updates, such as updates that provide stability or performance improvements.</span></span> <span data-ttu-id="77440-168">고려해야 할 주요 두 가지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-168">The two primary things you need to consider are :</span></span>
  
- <span data-ttu-id="77440-169">어디에서 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-169">Where do you want to get updates from</span></span>
    
- <span data-ttu-id="77440-170">기능 업데이트를 얼마나 자주 사용하겠는가</span><span class="sxs-lookup"><span data-stu-id="77440-170">How often do you want to get feature updates</span></span>
    
<span data-ttu-id="77440-171">업데이트의 위치를 제어하고 기능 업데이트를 얼마나 자주 받을지 제어할 수 있는 동안 어떤 특정 보안 업데이트나 비보안 업데이트를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-171">While you can control where you get updates from and how often you get feature updates, you can't choose which specific security updates or non-security updates you get.</span></span>
  
 <span data-ttu-id="77440-172">**어디에서 업데이트를 받을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="77440-172">**Where to get updates from**</span></span>
  
<span data-ttu-id="77440-173">기본적으로 비즈니스용 Skype 앱을 설치한 후 Microsoft에서 사용할 수 있는 경우 업데이트가 인터넷에서 자동으로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="77440-173">By default, after the Skype for Business app is installed, updates will be automatically downloaded from the Internet when they are available from Microsoft.</span></span> <span data-ttu-id="77440-174">업데이트가 발생하는 경우 또는 업데이트가 설치된 위치를 더 제어하려는 경우 Office 배포 도구 또는 그룹 정책을 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-174">If you want more control over when updates occur or where the updates are installed from, you can use the Office Deployment Tool or Group Policy to configure that.</span></span>
  
<span data-ttu-id="77440-175">예를 들어 많은 조직에서 조직 전체에 배포하기 전에 사용자 그룹으로 업데이트를 테스트하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-175">For example, many organizations want to test updates with a group of users before deploying them throughout the organization.</span></span> <span data-ttu-id="77440-176">Office 배포 도구 또는 그룹 정책을 사용하여 비즈니스용 Skype 앱을 구성하여 인터넷에서 자동으로 업데이트하는 대신 네트워크의 특정 위치에서 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-176">You can do this by using the Office Deployment Tool or Group Policy to configure the Skype for Business app to get updates from a specific location on your network, instead of automatically from the Internet.</span></span> <span data-ttu-id="77440-177">그런 다음 Office 배포 도구를 사용하여 매월 업데이트를 로컬 네트워크에 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-177">Then, you can use the Office Deployment Tool to download the updates every month to your local network.</span></span>
  
<span data-ttu-id="77440-178">Office 365 소프트웨어의 업데이트 작동 방식에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77440-178">For more information about how updates work for Office 365 software, see these articles:</span></span>
  
- [<span data-ttu-id="77440-179">엔터프라이즈용 Microsoft 365 Apps의 업데이트 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="77440-179">Overview of the update process for Microsoft 365 Apps for enterprise</span></span>](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [<span data-ttu-id="77440-180">엔터프라이즈용 Microsoft 365 Apps에 대한 업데이트를 관리하는 방법 선택</span><span class="sxs-lookup"><span data-stu-id="77440-180">Choose how to manage updates to Microsoft 365 Apps for enterprise</span></span>](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [<span data-ttu-id="77440-181">엔터프라이즈용 Microsoft 365 Apps에 대한 업데이트 설정 구성</span><span class="sxs-lookup"><span data-stu-id="77440-181">Configure update settings for Microsoft 365 Apps for enterprise</span></span>](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  <span data-ttu-id="77440-182">**기능 업데이트를 얼마나 자주 받을 수 있는가**</span><span class="sxs-lookup"><span data-stu-id="77440-182">**How often to get feature updates**</span></span>
  
<span data-ttu-id="77440-183">업데이트를 받을 위치 외에도 비즈니스용 Skype 클라이언트에 대한 새 기능을 얼마나 자주 받을지 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-183">In addition to where you get updates from, you can also control how often you get new features for the Skype for Business client.</span></span> <span data-ttu-id="77440-184">두 가지 선택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-184">The two choices are the following:</span></span>
  
- <span data-ttu-id="77440-185">새 기능이 있는 경우 매월 기능 업데이트 다운로드</span><span class="sxs-lookup"><span data-stu-id="77440-185">Get feature updates every month, if there are new features</span></span>
    
- <span data-ttu-id="77440-186">6개월마다 기능 업데이트 다운로드</span><span class="sxs-lookup"><span data-stu-id="77440-186">Get features updates every six months</span></span>
    
<span data-ttu-id="77440-187">일부 조직에서는 새 기능을 테스트하는 시간을 원하기 때문에 매월 기능 업데이트를 1년에 두 번만 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-187">For some organizations, they want time to test new features, so they want to get feature updates only twice a year instead of every month.</span></span>
  
<span data-ttu-id="77440-188">Office 배포 도구 또는 그룹 정책을 사용하여 업데이트 채널을 구성하여 기능 업데이트를 얼마나 자주 받을지 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77440-188">You can control how often you get feature updates by using the Office Deployment Tool or Group Policy to configure the update channel.</span></span> <span data-ttu-id="77440-189">월간 채널은 매월 기능 업데이트를 제공하는 반면, Semi-Annual 채널은 6개월마다 기능 업데이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77440-189">The Monthly Channel gives you feature updates monthly (approximately), while the Semi-Annual Channel gives you feature updates every six months.</span></span> <span data-ttu-id="77440-190">채널에 대한 자세한 내용은 [엔터프라이즈용 Microsoft 365 Apps의 업데이트 채널 개요를 참조하세요.](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)</span><span class="sxs-lookup"><span data-stu-id="77440-190">For more information about channels, see [Overview of update channels for Microsoft 365 Apps for enterprise](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="77440-191">관련 항목</span><span class="sxs-lookup"><span data-stu-id="77440-191">Related topics</span></span>

[<span data-ttu-id="77440-192">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="77440-192">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="77440-193">비즈니스용 Skype 및 Microsoft Teams 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="77440-193">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
