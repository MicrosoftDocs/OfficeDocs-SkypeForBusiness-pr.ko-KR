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
description: 클라우드 커넥터 기기를 배포 하 고 전화 시스템 (Cloud PBX)과 함께 사용 하도록 준비 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d00002719ed8aaac7d0f0fb0e5ceb5722acc289c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220068"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="c8b1f-103">클라우드 커넥터 어플라이언스 준비</span><span class="sxs-lookup"><span data-stu-id="c8b1f-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="c8b1f-104">클라우드 커넥터 기기를 배포 하 고 전화 시스템 (Cloud PBX)과 함께 사용 하도록 준비 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="c8b1f-105">이 섹션에서는 비즈니스용 Skype 클라우드 커넥터 버전 설치 파일을 가져오고, 클라우드 커넥터 소프트웨어를 설치 하 고, 클라우드 커넥터 기기를 배포 하기 위해 준비 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="c8b1f-106">이 섹션의 모든 단계를 완료 한 후에는 단일 사이트 또는 여러 사이트에 대해 클라우드 커넥터를 배포할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="c8b1f-107">기존 클라우드 커넥터 배포가 있고 아직 클라우드 커넥터 버전 2.1으로 업그레이드 하지 않은 경우 [새 버전의 클라우드 커넥터로 업그레이드를](upgrade-to-a-new-version-of-cloud-connector.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c8b1f-108">Microsoft는 클라우드 커넥터 에디션 버전 2.1의 현재 버전을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="c8b1f-109">자동 업데이트를 구성한 경우 클라우드 커넥터가 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="c8b1f-110">수동 업데이트를 구성한 경우에는 릴리스 후 60 일 이내에 버전 2.1으로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="c8b1f-111">Microsoft는 업그레이드 시간을 허용 하기 위해 2.1 릴리스 이후 60 일 동안 이전 버전을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="c8b1f-112">클라우드 커넥터 버전 2.1 이상에서는 호스트 어플라이언스에 .NET Framework 4.6.1 이상이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c8b1f-113">배포를 성공적으로 수행 하려면 cmdlet을 실행 하 여 비즈니스용 Skype 클라우드 Connector Edition을 구성 하는 경우에는 항상 시작 했던 것과 동일한 콘솔 세션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="c8b1f-114">배포 및 구성 중에 다른 세션으로 전환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="c8b1f-115">배포의 첫 번째 기기에 대해 수행 하는 몇 가지 단계는 사이트 디렉터리에 대 한 공유를 만들고 비트를 다운로드 한 다음 Windows Server ISO 이미지에서 가상 하드 디스크 (VHDX) 파일을 준비 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="c8b1f-116">비즈니스용 Skype 클라우드 Connector Edition 설치 관리자 다운로드</span><span class="sxs-lookup"><span data-stu-id="c8b1f-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="c8b1f-117">클라우드 커넥터 Vm이 실행 될 호스트 서버에서 설치 파일을 다운로드 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="c8b1f-118">설치 하는 동안 추가 파일을 다운로드 하기 때문에 클라우드 커넥터 설치 중에 호스트 서버에서 인터넷에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="c8b1f-119">설치 관리자를 실행 하 고 설치할 때 기본값을 그대로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="c8b1f-120">설치가 성공적으로 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="c8b1f-121">설치 확인 및 환경 구성</span><span class="sxs-lookup"><span data-stu-id="c8b1f-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="c8b1f-122">PowerShell 콘솔을 관리자 권한으로 열고 다음 cmdlet을 사용 하 여 비즈니스용 Skype 클라우드 Connector Edition cmdlet을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="c8b1f-123">이 명령은 비즈니스용 Skype 클라우드 커넥터 Edition에 대 한 cmdlet 목록을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="c8b1f-124">Vhd, SfBBits 및 VersionInfo 파일은 **사이트 디렉터리**에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="c8b1f-125">다음 cmdlet을 사용 하 여 **사이트 디렉터리** 의 위치를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="c8b1f-126">이 명령은 파일 시스템에서 위치를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-126">The command should return a location in your file system.</span></span> <span data-ttu-id="c8b1f-127">위치는 로컬 폴더 또는 파일 공유 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="c8b1f-128">**사이트 디렉터리** 의 기본 위치 는%USERPROFILE%\CloudConnector\SiteRoot.입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="c8b1f-129">기본 위치는 각 사이트에서 만들어지는 첫 번째 기기의 파일 공유로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="c8b1f-130">선택한 위치는 다음을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-130">The location you select must be:</span></span>

   - <span data-ttu-id="c8b1f-131">각 사이트에 만들어지는 첫 번째 기기에서 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="c8b1f-132">같은 사이트에 있는 다른 호스트 서버 (기기)에서 액세스할 수 있는 공유 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="c8b1f-133">**사이트 디렉터리** 를 기본 위치가 아닌 다른 위치로 설정 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="c8b1f-134">사이트에 대 한 HA (고가용성)를 배포 하는 경우에는 cmdlet을 실행 하 여 사이트 내의 각 호스트 서버에서 동일한 위치로 **사이트 디렉터리** 를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="c8b1f-135">사이트에 각 기기를 로그온 하 고 배포할 때 현재 로그온 계정에 **사이트 디렉터리**에 대 한 올바른 액세스 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="c8b1f-136">**기기 디렉터리** 는 비즈니스용 Skype 클라우드 커넥터 Edition의 로컬 작업 루트 디렉터리이 고 외부 인증서, 인스턴스 및 로그가 저장 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="c8b1f-137">기본 위치:%USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="c8b1f-138">**기기 디렉터리**의 위치를 찾으려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="c8b1f-139">기본 위치가 아닌 다른 위치로 **기기 디렉터리** 를 설정 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="c8b1f-140">기기 디렉터리는 기기의 로컬 폴더로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="c8b1f-141">비즈니스용 Skype 클라우드 Connector Edition 배포를 시작 하기 전에 **기기 디렉터리만** 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="c8b1f-142">배포 후에 변경 하는 경우에는 호스트 서버를 다시 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c8b1f-143">**기기 디렉터리** 경로에는 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="c8b1f-144">외부에 지 인증서에 대 한 경로 설정</span><span class="sxs-lookup"><span data-stu-id="c8b1f-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="c8b1f-145">다음 cmdlet를 실행 하 여 파일 이름을 포함 하는 경로를 외부에 지 인증서에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-145">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="c8b1f-146">예: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-146">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="c8b1f-147">인증서에 개인 키가 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-147">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="c8b1f-148">-Target 매개 변수는 버전 1.4.2 이상에 한정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="c8b1f-149">파일 이름을 포함 하 여 외부 인증서의 전체 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="c8b1f-150">인증서는 로컬로 저장 하거나 파일 공유에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="c8b1f-151">인증서가 공유 폴더에 저장 되어 있는 경우에는 각 사이트의 첫 번째 기기에 공유 폴더를 만들어야 하며, 같은 사이트에 속하는 다른 기기에서 액세스 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="c8b1f-152">이 cmdlet은 외부 인증서를 **기기 디렉터리로**복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c8b1f-153">**클라우드 커넥터 버전 1.4.2 이상으로 업데이트 한 경우**준비 된 외부 인증서에 개인 키 및 전체 인증서 체인 (루트 ca 인증서 및 중개 CA 인증서 포함)이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="c8b1f-154">**클라우드 커넥터 버전 1.4.2로 아직 업데이트 하지 않은 경우**준비 된 외부 인증서에 개인 키가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="c8b1f-155">이 외부 인증서는 Windows에서 신뢰할 수 있는 인증 기관이 기본적으로 발급 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="c8b1f-156">외부 PSTN 게이트웨이/SBC 인증서에 대 한 경로 설정</span><span class="sxs-lookup"><span data-stu-id="c8b1f-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="c8b1f-157">중재 서버와 PSTN 게이트웨이/SBC 간에 TLS를 사용 하는 경우에는 다음 cmdlet을 실행 하 여 파일 이름을 포함 한 경로를 게이트웨이 인증서에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="c8b1f-158">예: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="c8b1f-159">인증서에는 게이트웨이에 할당 된 인증서의 중간 체인과 루트 CA가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="c8b1f-160">-Target 매개 변수는 버전 1.4.2 이상에 한정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="c8b1f-161">Hyper-v 관리자에서 가상 스위치 만들기</span><span class="sxs-lookup"><span data-stu-id="c8b1f-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="c8b1f-162">**Hyper-v 관리자**  >  **가상 스위치 관리자**를 열고 **새 가상 스위치 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="c8b1f-163">외부 가상 스위치를 만들고 내부 네트워크 도메인에 연결 된 실제 네트워크 어댑터에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="c8b1f-164">이 가상 스위치에 대해 **관리 운영 체제에서이 네트워크 어댑터를 공유 하도록 허용을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="c8b1f-165">외부 가상 스위치를 만들어 인터넷으로 라우팅되는 실제 네트워크 어댑터에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="c8b1f-166">이 가상 스위치에 대 한 **이 네트워크 어댑터를 공유 하도록 허용 관리 운영 체제를** 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="c8b1f-167">경계 네트워크를 연결 하는 스위치의 이름을 내부 네트워크 도메인 **SFB CCE Corpnet 스위치**에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="c8b1f-168">경계 네트워크를 연결 하는 스위치의 이름을 인터넷 **SFB CCE Internet 스위치**에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="c8b1f-169">CloudConnector .ini 구성 파일 업데이트</span><span class="sxs-lookup"><span data-stu-id="c8b1f-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="c8b1f-170">[비즈니스용 Skype 클라우드 Connector Edition 계획](plan-skype-for-business-cloud-connector-edition.md) 의 [배포 매개 변수 결정](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) 에서 수집한 정보를 사용 하 여 cloudconnector .ini 파일을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="c8b1f-171">파일을 업데이트 하려면 먼저 다음 cmdlet을 실행 하 여 샘플 서식 파일 (CloudConnector. .ini)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="c8b1f-172">이 예제 템플릿은 **기기 디렉터리**에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="c8b1f-173">해당 환경의 값을 사용 하 여 업데이트 한 후에는 해당 파일을 **기기 디렉터리**에 있는 cloudconnector로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="c8b1f-174">**CcApplianceDirectory** 를 실행 하 여 **기기 디렉터리**에 대 한 경로를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="c8b1f-175">.Ini 파일을 업데이트 하는 경우 다음 사항을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="c8b1f-176">이 섹션에서는 여기에서 특별히 고려해 야 할 일부 값만 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="c8b1f-177">전체 목록은 [비즈니스용 Skype 클라우드 Connector Edition 계획](plan-skype-for-business-cloud-connector-edition.md) 의 [배포 매개 변수 결정](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="c8b1f-178">추가 기기나 새 사이트에서 변경 해야 하는 값에 대 한 자세한 내용은 [클라우드 커넥터의 여러 사이트 배포](deploy-multiple-sites-in-cloud-connector.md)항목의 [다중 사이트 배포에 대 한 HA (고가용성)를 사용 하 여 단일 사이트 비교](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="c8b1f-179">**SiteName:** 기본값은 **Site1**입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-179">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="c8b1f-180">**등록-CcAppliance** 를 실행 하 여 기존 사이트나 새 사이트에 기기를 등록할 때 Cmdlet이 **SiteName** 을 사용 하 여 등록할 사이트를 결정 하므로 클라우드 커넥터를 배포 하기 전에이를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-180">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="c8b1f-181">새 사이트에 기기를 등록 하려는 경우 **SiteName** 의 값은 고유 하 고 기존 사이트와 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="c8b1f-182">기존 사이트에 기기를 등록 하려는 경우 .ini 파일의 **SiteName** 에 대 한 값이 Microsoft 365 또는 Office 365 조직 구성에 정의 된 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="c8b1f-183">한 사이트에서 다른 사이트로 구성 파일을 복사 하는 경우에는 각 사이트의 **SiteName** 에 해당 하는 값을 적절 하 게 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="c8b1f-184">**ServerName:** 서버 이름에는 도메인 이름을 포함할 수 없으며 15 자로 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="c8b1f-185">**하드를 다시 입력 합니다.** 이 값을 null로 설정 하거나 비워 두지 않으면 기본값인 **Normal** 이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="c8b1f-186">[비즈니스용 Skype 클라우드 Connector Edition 계획](plan-skype-for-business-cloud-connector-edition.md)에 설명 된 대로 호스트 컴퓨터당 동시 통화를 500 지원 하기 위해 더 큰 버전의 클라우드 커넥터를 배포 하려는 경우에는 **Normal** 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="c8b1f-187">50 동시 통화를 지 원하는 더 작은 배포의 경우에는 **최소값** 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="c8b1f-188">**Internet/Corpnet/Management 가상 스위치:**: 만든 가상 스위치의 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="c8b1f-189">관리 가상 스위치의 경우 기본값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="c8b1f-190">배포 스크립트는 배포 시작 부분에 관리 가상 스위치를 만들고 배포가 완료 되 면이를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="c8b1f-191">**ManagementIPPrefix:** 네트워크 섹션의 ManagementIPPrefix 다른 내부 Ip와 다른 서브넷 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-191">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="c8b1f-192">예를 들어 기본값에 표시 되는 것 처럼, ManagementIPPrefix는 192.168.213.0이 고 AD IPAddress는 192.168.0.238입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-192">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="c8b1f-193">배포 스크립트에서는 각 가상 컴퓨터에 관리 네트워크 어댑터를 만들고 관리 IP를 할당 한 다음 관리 가상 스위치에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-193">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="c8b1f-194">이렇게 하면 호스트 서버가이 관리 네트워크를 통해 각 가상 컴퓨터에 연결 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-194">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="c8b1f-195">배포가 완료 되 면 관리 가상 스위치가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-195">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="c8b1f-196">**기본 VM 관련 구성:** 이 섹션의 설정은 **Convert-CcIsoToVhdx** cmdlet에 대해 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="c8b1f-197">기본 VM 이미지 준비를 진행 하는 동안 기본 VM이 내부 네트워크 스위치에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-197">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="c8b1f-198">다음 설정은 VM이 인터넷에 액세스 하기 위해 반드시 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-198">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="c8b1f-199">대개 BaseVMIP: 기본 VM에 할당할 corpnet IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="c8b1f-200">사설망 CorpnetDefaultGateway: 기본 VM에 할당할 기본 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="c8b1f-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="c8b1f-201">사설망 CorpnetDNSIPAddress: 기본 VM에 할당할 DNS IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="c8b1f-202">사설망 WSUSServer: Windows Server 업데이트 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="c8b1f-203">사설망 WSUSStatusServer: Windows Server Update Service 상태 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="c8b1f-204">사설망 EnableReferSupport:이 기능을 사용 하면 SIP 참조 지원 여부를 IP/PBX로 설정 하는 방법을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="c8b1f-205">**내부 Ip:**</span><span class="sxs-lookup"><span data-stu-id="c8b1f-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="c8b1f-206">서브넷 마스크 CorpnetIPPrefixLength 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="c8b1f-207">이러한 내부 Ip에 대해 IP 충돌이 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="c8b1f-208">**외부 Ip:**</span><span class="sxs-lookup"><span data-stu-id="c8b1f-208">**External IPs:**</span></span>

  - <span data-ttu-id="c8b1f-209">MR 공용 IP: 비 NAT 또는 NAT에 대해 ExternalMRIPs (ExternalMRPublicIPs)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="c8b1f-210">ExternalSIPIPs 및 ExternalMRIPs도 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="c8b1f-211">서브넷 마스크 InternetIPPrefixLength 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="c8b1f-212">이러한 외부 Ip에 IP 충돌이 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="c8b1f-213">**게이트웨이에서**</span><span class="sxs-lookup"><span data-stu-id="c8b1f-213">**Gateways:**</span></span>

  - <span data-ttu-id="c8b1f-214">게이트웨이가 하나뿐인 경우에는 보조 게이트웨이의 섹션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-214">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="c8b1f-215">게이트웨이가 두 개 이상 있는 경우 기존 게이트웨이를 복사 하 여 붙여 넣고 업데이트 하 여 추가 섹션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-215">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="c8b1f-216">게이트웨이의 IP 주소와 포트가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="c8b1f-217">PSTN 게이트웨이 수준 HA를 지원 하려면 보조 게이트웨이를 떠나 사용할 추가 게이트웨이를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="c8b1f-218">기존 항목을 복사 하 여 붙여 넣고 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="c8b1f-219">필요에 따라 LocalRoute 값을 업데이트 하 여 아웃 바운드 통화 번호를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="c8b1f-220">사이트 디렉터리에 비트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="c8b1f-221">다음 cmdlet를 실행 하 여 **사이트 디렉터리**에 비트 및 버전 정보 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="c8b1f-222">첫 번째 어플라이언스에 대해서만이 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="c8b1f-223">다운로드 한 ISO 파일에서 VHDX (기본 가상 디스크) 준비</span><span class="sxs-lookup"><span data-stu-id="c8b1f-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="c8b1f-224">이 단계에서는 Windows Server 2012 ISO 이미지에서 VHDX (가상 하드 디스크) 파일을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="c8b1f-225">VHDX는 배포 중에 가상 컴퓨터를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="c8b1f-226">임시 가상 컴퓨터 (기본 VM)가 생성 되 고 ISO 파일에서 Windows Server 2012이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="c8b1f-227">VM을 만든 후에는 필요한 구성 요소 중 일부를 설치 하 고 최신 Windows 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="c8b1f-228">마지막에는 기본 VM이 일반화 (sysprep) 되 고 정리 되어 생성 된 가상 디스크 파일만 남게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="c8b1f-229">첫 번째 어플라이언스에 대해서만이 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="c8b1f-230">이 단계를 진행 하기 전에 corpnet 스위치를 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-230">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="c8b1f-231">또한 CloudConnector .ini 파일에서 다음 설정이 올바르게 구성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-231">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="c8b1f-232">사설망 CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="c8b1f-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="c8b1f-233">대개 BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="c8b1f-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="c8b1f-234">사설망 CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="c8b1f-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="c8b1f-235">사설망 CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="c8b1f-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="c8b1f-236">사설망 CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="c8b1f-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="c8b1f-237">관리자로 PowerShell 콘솔을 시작 하 고 다음 cmdlet을 실행 하 여 ISO 이미지를 VHD (가상 하드 디스크)로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="c8b1f-238">파일 이름을 포함 하는 전체 경로를 ISO 이미지에 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-238">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="c8b1f-239">예: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-239">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="c8b1f-240">만들어진 VHD 파일은 **Site Directory** \Bits\vhd 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="c8b1f-241">**Get-CcSiteDirectory**를 실행 하 여 **사이트 디렉터리** 의 경로를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8b1f-242">기본적으로 프록시 설정은 기본 VM에 대해 구성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="c8b1f-243">네트워크 환경에서 Windows Update를 통해 VM을 업데이트 하기 위해 프록시가 필요한 경우 "Convert-Ccitovhdx"를 실행할 때-PauseBeforeUpdate 스위치를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="c8b1f-244">Windows 업데이트 전에 스크립트를 일시 중지 하 고 VM에서 프록시를 수동으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="c8b1f-245">프록시를 설정 하 고 VM이 인터넷에 액세스할 수 있는 후에는 스크립트를 다시 시작 하 여 나머지 단계를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="c8b1f-246">다중 사이트 배포용 Vhd 만들기</span><span class="sxs-lookup"><span data-stu-id="c8b1f-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="c8b1f-247">이 단계는 다중 사이트 배포에만 적용 되는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="c8b1f-248">다중 사이트 배포를 배포 하는 경우 ISO를 각 사이트의 VHD로 변환 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-248">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="c8b1f-249">첫 번째 사이트에 대해 만들어진 VHDX를 두 번째 사이트의 호스트 서버에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-249">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="c8b1f-250">추가 사이트의 호스트 서버에서 동일한 파일 위치 ( **사이트 디렉터리** \Bits\vhd 폴더)와 동일한 파일 이름으로 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="c8b1f-251">PowerShell 실행 정책을 RemoteSigned로 설정</span><span class="sxs-lookup"><span data-stu-id="c8b1f-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="c8b1f-252">제공 된 PowerShell 스크립트를 수행 하려면 실행 정책을 RemoteSigned로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-252">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="c8b1f-253">현재 설정을 보려면 PowerShell 콘솔을 관리자 권한으로 열고 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-253">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="c8b1f-254">"RemoteSigned"로 설정 되지 않은 경우 다음 cmdlet을 실행 하 여 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="c8b1f-255">호스트 컴퓨터의 로컬 그룹 정책 변경 (1.4.1 및 이전 버전)</span><span class="sxs-lookup"><span data-stu-id="c8b1f-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="c8b1f-256">이 작업은 클라우드 커넥터 버전 1.4.2 이상에는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="c8b1f-257">CceService 계정은 비즈니스용 Skype 클라우드 커넥터 에디션 배포 중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="c8b1f-258">클라우드 커넥터 관리 서비스가 실행 되며 cloudconnector .msi를 제거 하는 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="c8b1f-259">사용자가 로그 오프할 때 사용자 레지스트리가 언로드되지 않도록 지정 하려면 클라우드 커넥터 호스트 컴퓨터에서 그룹 정책 설정을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="c8b1f-260">아래 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="c8b1f-261">그룹 정책 설정을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="c8b1f-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="c8b1f-262">Gpedit.msc를 실행 하 여 **그룹 정책 편집기** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="c8b1f-263">**그룹 정책 편집기**에서 관리 템플릿으로 이동 합니다 > System > UserProfile > 사용자 로그 오프할 때 사용자 레지스트리를 강제로 언로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="c8b1f-264">해당 값을 **Enabled**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="c8b1f-265">Microsoft 365 또는 Office 365 조직 설정</span><span class="sxs-lookup"><span data-stu-id="c8b1f-265">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="c8b1f-266">비즈니스용 Skype Online 및 전화 시스템을 사용 하는 Microsoft 365 또는 Office 365 조직이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-266">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="c8b1f-267">클라우드 커넥터 사용을 시도 하기 전에 테 넌 트가 설정 및 구성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="c8b1f-268">일부 Microsoft 365 및 Office 365 설치 단계를 수행 하려면 TRPS (테 넌 트 원격 PowerShell)를 사용 하 여 Microsoft 365 또는 Office 365 조 직을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-268">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="c8b1f-269">**이를 호스트 서버에 설치 해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c8b1f-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="c8b1f-270">비즈니스용 skype Online 모듈을 다운로드 하는 데에는 Skype for [Business online, Windows PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="c8b1f-271">클라우드 커넥터 온라인 관리를 위한 전용 비즈니스용 Skype 관리자 계정을 만듭니다 (예: CceOnlineManagmentAdministrator).</span><span class="sxs-lookup"><span data-stu-id="c8b1f-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="c8b1f-272">이 계정은 기기에서 기기를 추가 또는 제거 하거나, 자동 OS 업데이트를 사용 하거나 사용 하지 않도록 설정 하거나, 자동 이진 업데이트를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="c8b1f-273">이 계정의 암호가 만료 되지 않도록 설정 하 여 만료 될 때마다 서비스에 대해 변경할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


