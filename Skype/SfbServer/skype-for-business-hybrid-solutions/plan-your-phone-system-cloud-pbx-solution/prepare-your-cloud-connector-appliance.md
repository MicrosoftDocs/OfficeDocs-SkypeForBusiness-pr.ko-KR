---
title: 클라우드 커넥터 어플라이언스 준비
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Phone System(클라우드 PBX)에서 배포 및 사용을 위해 클라우드 커넥터 어플라이언스를 준비하는 방법을 설명합니다.
ms.openlocfilehash: 536e9b98520e4274e00d43d57224267f5b824dc9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092636"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="434e7-103">클라우드 커넥터 어플라이언스 준비</span><span class="sxs-lookup"><span data-stu-id="434e7-103">Prepare your Cloud Connector appliance</span></span>

> [!Important]
> <span data-ttu-id="434e7-104">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="434e7-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="434e7-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="434e7-106">Phone System(클라우드 PBX)에서 배포 및 사용을 위해 클라우드 커넥터 어플라이언스를 준비하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-106">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="434e7-107">이 섹션에서는 비즈니스용 Skype 클라우드 커넥터 버전 설치 파일을 다운로드하고, 클라우드 커넥터 소프트웨어를 설치하고, 배포를 위해 클라우드 커넥터 어플라이언스를 준비하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-107">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="434e7-108">이 섹션의 모든 단계를 완료하면 단일 사이트 또는 여러 사이트에 대해 클라우드 커넥터를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-108">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="434e7-109">기존 클라우드 커넥터 배포가 있는 경우 아직 클라우드 커넥터 버전 2.1로 업그레이드하지 않은 경우 [Upgrade to a new version of Cloud Connector을 참조합니다.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="434e7-109">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="434e7-110">Microsoft는 현재 버전의 Cloud Connector Edition 버전 2.1을 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-110">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="434e7-111">자동 업데이트를 구성한 경우 클라우드 커넥터가 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-111">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="434e7-112">수동 업데이트를 구성한 경우 릴리스 후 60일 이내에 버전 2.1로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-112">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="434e7-113">Microsoft는 2.1 릴리스 이후 60일 동안 이전 버전을 지원하여 업그레이드 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-113">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="434e7-114">클라우드 커넥터 버전 2.1 이상의 경우 호스트 어플라이언스에 4.6.1 .NET Framework 이상이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-114">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="434e7-115">성공적인 배포를 위해 cmdlet을 실행하여 비즈니스용 Skype 클라우드 커넥터 에디션을 구성할 때 항상 시작한 콘솔 세션과 동일한 콘솔 세션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="434e7-115">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="434e7-116">배포 및 구성 중에 다른 세션으로 전환하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-116">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="434e7-117">배포의 첫 번째 어플라이언스에 한해 사이트 디렉터리에 대한 공유 만들기, 비트 다운로드, Windows Server ISO 이미지에서 VHDX(가상 하드 디스크) 파일 준비 등 몇 가지 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-117">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="434e7-118">비즈니스용 Skype 클라우드 커넥터 버전 설치 관리자 다운로드</span><span class="sxs-lookup"><span data-stu-id="434e7-118">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="434e7-119">클라우드 커넥터 VM이 실행될 호스트 서버에서 설치 파일을 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 다운로드합니다. .</span><span class="sxs-lookup"><span data-stu-id="434e7-119">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="434e7-120">설치하는 동안 추가 파일이 다운로드될 수 있기 때문에 클라우드 커넥터를 설치하는 동안 호스트 서버가 인터넷에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-120">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="434e7-121">설치 관리자를 실행하고 설치 중에 기본값을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-121">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="434e7-122">설치가 성공적으로 완료 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-122">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="434e7-123">설치 확인 및 환경 구성</span><span class="sxs-lookup"><span data-stu-id="434e7-123">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="434e7-124">관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 사용하여 비즈니스용 Skype 클라우드 커넥터 버전 cmdlet을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-124">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="434e7-125">이 명령은 비즈니스용 Skype 클라우드 커넥터 버전에 대한 cmdlet 목록을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-125">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="434e7-126">VHD, SfBBits 및 VersionInfo 파일은 사이트 디렉터리에 **저장됩니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-126">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="434e7-127">다음 cmdlet을 사용하여 **사이트** 디렉터리의 위치를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-127">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="434e7-128">명령은 파일 시스템의 위치를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-128">The command should return a location in your file system.</span></span> <span data-ttu-id="434e7-129">위치는 로컬 폴더 또는 파일 공유일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-129">The location can be a local folder or a file share.</span></span> <span data-ttu-id="434e7-130">사이트 디렉터리의 기본 **위치는** %USERPROFILE%\CloudConnector\SiteRoot입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-130">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="434e7-131">기본 위치는 각 사이트에서 만든 첫 번째 어플라이언스에서 파일 공유로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-131">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="434e7-132">선택한 위치는 다음을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-132">The location you select must be:</span></span>

   - <span data-ttu-id="434e7-133">각 사이트에서 만든 첫 번째 어플라이언스에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-133">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="434e7-134">같은 사이트의 다른 호스트 서버(어플라이언스)에서 액세스할 수 있는 공유 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-134">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="434e7-135">사이트 **디렉터리를** 기본값이 다른 위치로 설정하기 위해 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-135">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="434e7-136">사이트에 대해 HA(고가용성)를 배포하는 경우 cmdlet을 실행하여 사이트 디렉터리를 사이트 내의 각 호스트 서버의 동일한 위치로 설정해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="434e7-136">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="434e7-137">사이트에 로그온하여 각 어플라이언스를 배포할 때 현재 로그온 계정에 사이트 디렉터리에 대한 올바른 액세스 **권한이 있는지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-137">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="434e7-138">**Appliance Directory는** 비즈니스용 Skype 클라우드 커넥터 버전에 대한 로컬 작업 루트 디렉터리로, 외부 인증서, 인스턴스 및 로그가 저장되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-138">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="434e7-139">기본 위치는 %USERPROFILE%\CloudConnector\ApplianceRoot입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-139">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="434e7-140">**Appliance Directory의** 위치를 찾으면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-140">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="434e7-141">**Appliance Directory를** 기본값이 다른 위치로 설정하기 위해 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-141">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="434e7-142">Appliance Directory는 어플라이언스의 로컬 폴더로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-142">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="434e7-143">비즈니스용 Skype 클라우드 커넥터 버전 배포를 시작하기 전에 **Appliance** 디렉터리만 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-143">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="434e7-144">배포 후에 변경하는 경우 호스트 서버를 다시 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-144">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="434e7-145">Appliance Directory **경로에는** 공백이 포함되어 있지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-145">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="434e7-146">외부 에지 인증서의 경로 설정</span><span class="sxs-lookup"><span data-stu-id="434e7-146">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="434e7-147">다음 cmdlet을 실행하여 파일 이름을 비롯한 경로를 외부 에지 인증서로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-147">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="434e7-148">예: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="434e7-148">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="434e7-149">인증서는 개인 키를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-149">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="434e7-150">-Target 매개 변수는 버전 1.4.2 이상과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-150">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="434e7-151">파일 이름을 포함하여 외부 인증서의 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-151">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="434e7-152">인증서는 로컬 또는 파일 공유에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-152">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="434e7-153">인증서가 공유 폴더에 저장된 경우 각 사이트의 첫 번째 어플라이언스에 공유 폴더를 만들어야 하며 동일한 사이트에 속하는 다른 어플라이언스에서 공유 폴더에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-153">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="434e7-154">이 cmdlet은 외부 인증서를 **Appliance Directory에 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-154">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="434e7-155">클라우드 커넥터 버전 **1.4.2** 이상으로 업데이트한 경우 준비된 외부 인증서에 개인 키와 루트 CA 인증서 및 중간 CA 인증서를 포함한 전체 인증서 체인이 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="434e7-155">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="434e7-156">**아직 클라우드 커넥터 버전 1.4.2로** 업데이트하지 않은 경우 준비된 외부 인증서에 개인 키가 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="434e7-156">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="434e7-157">이 외부 인증서는 기본적으로 Windows에서 신뢰하는 인증 기관에서 발급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-157">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="434e7-158">외부 PSTN 게이트웨이/SBC 인증서의 경로 설정</span><span class="sxs-lookup"><span data-stu-id="434e7-158">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="434e7-159">중재 서버와 PSTN 게이트웨이/SBC 간에 TLS를 사용하는 경우 다음 cmdlet을 실행하여 파일 이름을 비롯한 경로를 게이트웨이 인증서로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-159">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="434e7-160">예: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="434e7-160">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="434e7-161">인증서는 게이트웨이에 할당된 인증서에 대한 루트 CA 및 중간 체인을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-161">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="434e7-162">-Target 매개 변수는 버전 1.4.2 이상과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-162">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="434e7-163">Hyper-V 관리자에서 가상 스위치 만들기</span><span class="sxs-lookup"><span data-stu-id="434e7-163">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="434e7-164">Hyper-V **관리자** 가상 스위치 관리자를  >  **열고** 새 가상 스위치 **관리자 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-164">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="434e7-165">외부 가상 스위치를 만들고 내부 네트워크 도메인에 연결된 실제 네트워크 어댑터에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-165">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="434e7-166">이 가상 스위치에 대해 관리 **운영 체제에서** 이 네트워크 어댑터를 공유하도록 허용을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-166">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="434e7-167">외부 가상 스위치를 만들고 인터넷으로 라우팅된 실제 네트워크 어댑터에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-167">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="434e7-168">관리 운영 체제가 이 가상 스위치에 대해 이 **네트워크** 어댑터를 공유할 수 있도록 허용을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="434e7-169">경계 네트워크를 내부 네트워크 도메인 **SfB CCE Corpnet 스위치에** 연결하는 스위치의 이름을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="434e7-169">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="434e7-170">경계 네트워크를 인터넷 **SfB CCE** 인터넷 스위치에 연결하는 스위치의 이름을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="434e7-170">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="434e7-171">구성 CloudConnector.ini 업데이트</span><span class="sxs-lookup"><span data-stu-id="434e7-171">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="434e7-172">Plan [for Skype for Business Cloud Connector Edition의](plan-skype-for-business-cloud-connector-edition.md) CloudConnector.ini 매개 변수 결정에서 수집한 정보를 사용하여 파일 파일을 준비합니다. [](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)</span><span class="sxs-lookup"><span data-stu-id="434e7-172">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="434e7-173">파일을 업데이트하기 위해 먼저 다음 cmdlet을 실행하여 샘플 템플릿(CloudConnector.Sample.ini.</span><span class="sxs-lookup"><span data-stu-id="434e7-173">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="434e7-174">샘플 템플릿은 **Appliance Directory 에 저장됩니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-174">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="434e7-175">환경의 값으로 업데이트한 후 파일을 Appliance Directory CloudConnector.ini **저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-175">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="434e7-176">**Get-CcApplianceDirectory를** 실행하여 Appliance 디렉터리의 경로를 **확인할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-176">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="434e7-177">.ini 파일을 업데이트할 때 다음을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-177">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="434e7-178">이 섹션에서는 .ini 파일의 일부 값에 대해 설명하지는 않습니다. 특별한 고려 사항이 있는 값만 여기에 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-178">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="434e7-179">전체 목록은 [Plan](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) for Skype for Business Cloud Connector Edition 항목의 배포 매개 변수 결정 [섹션을 참조하세요.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="434e7-179">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="434e7-180">추가 어플라이언스 또는 새 사이트에 대해 변경해야 하는 값에 대한 자세한 내용은 Deploy multiple sites in Cloud Connector 항목의 [HA(고가용성)가](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) 포함된 단일 사이트와 다중 사이트 배포를 [참조하세요.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="434e7-180">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="434e7-181">**SiteName:** 기본값은 **Site1입니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-181">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="434e7-182">**Register-CcAppliance를** 실행하여 기존 또는 새 사이트에 어플라이언스를 등록할 때 Cmdlet은 **SiteName을** 사용하여 등록할 사이트를 결정하기 때문에 클라우드 커넥터를 배포하기 전에 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-182">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="434e7-183">어플라이언스를 새 사이트에 등록하려면 **SiteName** 값이 고유해야 하고 기존 사이트와 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-183">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="434e7-184">기존 사이트에 어플라이언스를 등록하려면 .ini 파일의 **SiteName** 값이 Microsoft 365 또는 Office 365 조직 구성에 정의된 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-184">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="434e7-185">한 사이트에서 다른 사이트로 구성 파일을 복사하는 경우 그에 따라 각 사이트에 **대해 SiteName** 값을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-185">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="434e7-186">**ServerName:** 서버 이름은 도메인 이름을 포함하지 말고 15자로 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-186">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="434e7-187">**HardwareType:** 값을 null로 설정하거나 설정하지 않은 경우 **Normal의** 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-187">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="434e7-188">**비즈니스용** Skype 클라우드 커넥터 버전 계획에 설명된 바와 같이 더 큰 버전의 클라우드 커넥터를 배포하여 호스트 컴퓨터당 500개 동시 통화를 지원할 계획인 경우 Normal을 [사용하세요.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="434e7-188">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="434e7-189">**동시** 통화 50회를 지원하는 소규모 배포에는 최소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-189">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="434e7-190">**인터넷/Corpnet/Management 가상 스위치:** 만든 가상 스위치의 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-190">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="434e7-191">관리 가상 스위치의 경우 기본값을 그대로 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-191">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="434e7-192">배포 스크립트는 배포 시작 시 관리 가상 스위치를 만들고 배포가 완료되면 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-192">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="434e7-193">**ManagementIPPrefix:** 네트워크 섹션의 ManagementIPPrefix는 다른 내부 IP와 다른 서브넷이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-193">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="434e7-194">예를 들어 기본값에 따르면 ManagementIPPrefix는 192.168.213.0인 반면 AD IPAddress는 192.168.0.238입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-194">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="434e7-195">배포 스크립트는 각 가상 컴퓨터에 관리 네트워크 어댑터를 만들고 관리 IP를 할당한 다음 관리 가상 스위치에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-195">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="434e7-196">이렇게 하면 호스트 서버가 이 관리 네트워크를 통해 각 가상 컴퓨터에 연결하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-196">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="434e7-197">배포가 완료되면 관리 가상 스위치가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-197">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="434e7-198">**VM 관련 기본 구성:** 이 섹션의 설정은 **Convert-CcIsoToVhdx** cmdlet에 대해 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-198">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="434e7-199">기본 VM 이미지 준비 중에는 기본 VM이 내부 네트워크 스위치에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-199">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="434e7-200">다음 설정은 VM이 인터넷에 액세스할 수 있도록 하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-200">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="434e7-201">[Common] BaseVMIP: 기본 VM에 할당할 corpnet IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-201">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="434e7-202">[네트워크] CorpnetDefaultGateway: 기본 VM에 할당할 기본 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-202">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="434e7-203">[네트워크] CorpnetDNSIPAddress: 기본 VM에 할당할 DNS IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-203">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="434e7-204">[네트워크] WSUSServer: Windows Server Update Service의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-204">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="434e7-205">[네트워크] WSUSStatusServer: Windows Server 업데이트 서비스 상태 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-205">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="434e7-206">[네트워크] EnableReferSupport: IP/PBX에 대한 트렁크 구성에서 SIP REFER 지원을 사용할지 여부를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-206">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="434e7-207">**내부 IPS:**</span><span class="sxs-lookup"><span data-stu-id="434e7-207">**Internal IPs:**</span></span>

  - <span data-ttu-id="434e7-208">서브넷 마스크 CorpnetIPPrefixLength가 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-208">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="434e7-209">이러한 내부 IP에 대한 IP 충돌이 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="434e7-209">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="434e7-210">**외부 IPS:**</span><span class="sxs-lookup"><span data-stu-id="434e7-210">**External IPs:**</span></span>

  - <span data-ttu-id="434e7-211">MR 공용 IP의 경우: NAT가 아닌 경우 ExternalMRIP 또는 NAT용 ExternalMRPublicIP를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-211">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="434e7-212">ExternalSIPIP와 ExternalMRIP는 동일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-212">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="434e7-213">서브넷 마스크 InternetIPPrefixLength가 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-213">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="434e7-214">이러한 외부 IP에 대한 IP 충돌이 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="434e7-214">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="434e7-215">**게이트웨이:**</span><span class="sxs-lookup"><span data-stu-id="434e7-215">**Gateways:**</span></span>

  - <span data-ttu-id="434e7-216">게이트웨이가 하나뿐인 경우 보조 게이트웨이에 대한 섹션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-216">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="434e7-217">게이트웨이가 두 개 이상인 경우 기존 게이트웨이를 복사하여 붙여넣은 다음 업데이트하여 추가 섹션을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="434e7-217">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="434e7-218">게이트웨이의 IP 주소와 포트가 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-218">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="434e7-219">PSTN 게이트웨이 수준 HA를 지원하기 위해 보조 게이트웨이를 그대로 두고 사용할 게이트웨이를 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-219">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="434e7-220">기존 항목을 복사하여 붙여넣은 다음 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-220">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="434e7-221">원하는 경우 LocalRoute 값을 업데이트하여 아웃바운드 통화 번호를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-221">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="434e7-222">비트를 사이트 디렉터리로 다운로드</span><span class="sxs-lookup"><span data-stu-id="434e7-222">Download the bits to the Site Directory</span></span>

<span data-ttu-id="434e7-223">다음 cmdlet을 실행하여 비트 및 버전 정보 파일을 사이트 디렉터리에 **다운로드합니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-223">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="434e7-224">첫 번째 어플라이언스에만 이 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-224">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="434e7-225">다운로드한 ISO 파일에서 기본 VHDX(가상 디스크) 준비</span><span class="sxs-lookup"><span data-stu-id="434e7-225">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="434e7-226">이 단계에서는 ISO 이미지의 VHDX(가상 하드 디스크) Windows Server 2012 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-226">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="434e7-227">VHDX는 배포 중에 가상 컴퓨터를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-227">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="434e7-228">임시 가상 컴퓨터(기본 VM)가 만들어지며 Windows Server 2012 ISO 파일에서 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-228">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="434e7-229">VM을 만든 후 몇 가지 필수 구성 요소가 설치되고 최신 Windows 업데이트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-229">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="434e7-230">결국 기본 VM이 일반화되고(sysprep) 정리되고 생성된 가상 디스크 파일만 남게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-230">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="434e7-231">첫 번째 어플라이언스에만 이 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-231">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="434e7-232">이 단계를 진행하기 전에 corpnet 스위치를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-232">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="434e7-233">또한 다음 설정이 파일에서 올바르게 CloudConnector.ini 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-233">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="434e7-234">[네트워크] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="434e7-234">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="434e7-235">[Common] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="434e7-235">[Common]BaseVMIP</span></span>

- <span data-ttu-id="434e7-236">[네트워크] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="434e7-236">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="434e7-237">[네트워크] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="434e7-237">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="434e7-238">[네트워크] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="434e7-238">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="434e7-239">관리자 권한으로 PowerShell 콘솔을 시작하고 다음 cmdlet을 실행하여 ISO 이미지를 VHD(가상 하드 디스크)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-239">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="434e7-240">파일 이름을 포함하여 ISO 이미지에 대한 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-240">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="434e7-241">예: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="434e7-241">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="434e7-242">생성된 VHD 파일은 사이트 디렉터리  \Bits\VHD 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-242">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="434e7-243">**Get-CcSiteDirectory 를** 실행하여 사이트 디렉터리의 경로를 얻을 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="434e7-243">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="434e7-244">기본적으로 프록시 설정은 기본 VM에서 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-244">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="434e7-245">네트워크 환경에서 Windows 업데이트를 통해 VM을 업데이트하기 위해 프록시가 필요한 경우 "Convert-CcIsoToVhdx"를 실행할 때 -PauseBeforeUpdate 스위치를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-245">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="434e7-246">스크립트는 Windows 업데이트 전에 일시 중지됩니다. VM에서 프록시를 수동으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-246">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="434e7-247">프록시를 설정하고 VM이 인터넷에 액세스할 수 있는 후 스크립트를 다시 시작하여 나머지 단계를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-247">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="434e7-248">다중 사이트 배포를 위한 VHD 만들기</span><span class="sxs-lookup"><span data-stu-id="434e7-248">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="434e7-249">이 단계는 다중 사이트 배포에만 적용되는 선택적 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-249">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="434e7-250">다중 사이트 배포를 배포하는 경우 각 사이트의 VHD로 ISO를 변환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-250">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="434e7-251">첫 번째 사이트에 대해 만든 VHDX를 두 번째 사이트의 호스트 서버에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-251">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="434e7-252">추가 사이트의 경우 호스트 서버에서 동일한 파일 **위치(Site Directory** \Bits\VHD 폴더)에 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-252">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="434e7-253">PowerShell 실행 정책을 RemoteSigned로 설정</span><span class="sxs-lookup"><span data-stu-id="434e7-253">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="434e7-254">제공된 PowerShell 스크립트를 사용하려면 실행 정책을 RemoteSigned로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-254">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="434e7-255">현재 설정을 표시하기 위해 관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-255">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="434e7-256">"RemoteSigned"로 설정되지 않은 경우 다음 cmdlet을 실행하여 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-256">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="434e7-257">호스트 컴퓨터의 로컬 그룹 정책 변경(버전 1.4.1 이전 버전)</span><span class="sxs-lookup"><span data-stu-id="434e7-257">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="434e7-258">클라우드 커넥터 버전 1.4.2 이상에서는 이 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-258">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="434e7-259">CceService 계정은 비즈니스용 Skype 클라우드 커넥터 버전 배포 중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-259">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="434e7-260">클라우드 커넥터 관리 서비스를 실행하며 클라우드 커넥터 관리 서비스를 제거하기 위한 권한이 cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="434e7-260">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="434e7-261">사용자가 로그오프할 때 사용자 레지스트리를 언로드하지 못하도록 지정하려면 클라우드 커넥터 호스트 컴퓨터의 그룹 정책 설정을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-261">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="434e7-262">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-262">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="434e7-263">그룹 정책 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-263">To change the Group Policy setting</span></span>

1. <span data-ttu-id="434e7-264">gpedit.msc를 실행하여 그룹 정책 편집기를 열 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="434e7-264">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="434e7-265">그룹 **정책 편집기에서** 관리 템플릿 > > UserProfile > 로그오프 시 사용자 레지스트리를 강제로 언로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-265">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="434e7-266">해당 값을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-266">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="434e7-267">Microsoft 365 또는 Office 365 조직 설정</span><span class="sxs-lookup"><span data-stu-id="434e7-267">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="434e7-268">비즈니스용 Skype Online 및 전화 시스템이 있는 Microsoft 365 또는 Office 365 조직이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-268">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="434e7-269">클라우드 커넥터를 사용하기 전에 테넌트가 설정 및 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="434e7-269">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="434e7-270">일부 Microsoft 365 및 Office 365 설치 단계를 수행하려면 TRPS(테넌트 원격 PowerShell)를 사용하여 Microsoft 365 또는 Office 365 조직을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-270">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="434e7-271">**이 서버는 호스트 서버에 설치해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="434e7-271">**This should be installed on the host server.**</span></span> <span data-ttu-id="434e7-272">PowerShell용 비즈니스용 Skype Online 모듈은 비즈니스용 Skype Online, 비즈니스용 Skype Windows PowerShell [다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="434e7-272">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="434e7-273">클라우드 커넥터 온라인 관리에 대한 전용 비즈니스용 Skype 관리자 계정(예: CceOnlineManagmentAdministrator)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-273">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="434e7-274">이 계정은 어플라이언스를 추가 또는 제거하고, 자동 OS 업데이트를 사용 또는 사용하지 않도록 설정하고, 자동 이진 업데이트를 사용 또는 사용하지 않도록 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-274">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="434e7-275">만료될 때마다 서비스에 대해 암호를 변경할 필요가 있도록 이 계정의 암호를 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="434e7-275">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>