---
title: 비즈니스용 Skype 서버에서 웹 서비스 구성 설정 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '요약: 비즈니스용 Skype 서버에서 웹 서비스 구성 설정을 관리합니다.'
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806498"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="acd99-103">비즈니스용 Skype 서버에서 웹 서비스 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="acd99-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="acd99-104">**요약:** 비즈니스용 Skype 서버에서 웹 서비스 구성 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="acd99-105">웹 서비스  페이지를 사용하여 비즈니스용 Skype 서버 관련 웹 서버 및 웹 서비스에 액세스하기 위한 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="acd99-106">다음 단계에 따라 새 웹 서비스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="acd99-107">새 웹 서비스 구성 설정을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="acd99-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="acd99-108">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="acd99-109">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="acd99-110">왼쪽 탐색 표시줄에서 **보안**, **웹 서비스** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="acd99-111">**웹 서비스** 페이지에서 **새로 만들기** 를 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="acd99-p101">사이트에 대해 웹 서비스를 구성하려면 **사이트 구성** 을 클릭합니다. **사이트 선택** 에서 웹 서비스 정책을 적용할 사이트를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="acd99-p102">풀에 대해 웹 서비스를 구성하려면 **풀 구성** 을 클릭합니다. **서비스 선택** 에서 웹 서비스 정책을 적용할 서비스를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="acd99-116">**새 웹 서비스 설정** 의 **통합 Windows 인증** 에서 **협상**, **통합 Windows 인증** 또는 **없음** 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="acd99-117">환경의 지원 및 클라이언트 기능에 따라 다음 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="acd99-118">**PIN 인증 사용** - PIN 번호를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="acd99-119">**인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="acd99-120">**인증서 체인 다운로드 사용** - 인증 인증서가 있는 서버에서 해당 인증서에 대해 인증서 체인을 다운로드하도록 합니다</span><span class="sxs-lookup"><span data-stu-id="acd99-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="acd99-121">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="acd99-122">기존 웹 서비스 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="acd99-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="acd99-123">웹 서비스  페이지를 사용하여 비즈니스용 Skype 서버 관련 웹 서버 및 웹 서비스에 액세스하기 위한 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="acd99-124">다음 단계에 따라 기존의 웹 서비스 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="acd99-125">기존 웹 서비스 구성 설정을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="acd99-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="acd99-126">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="acd99-127">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="acd99-128">왼쪽 탐색 표시줄에서 **보안**, **웹 서비스** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="acd99-129">**웹 서비스** 페이지에서 구성을 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="acd99-130">웹 **서비스 설정 편집의** **Windows 통합 인증에서** **협상,** Windows 통합 **인증** 또는 없음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="acd99-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="acd99-131">환경의 지원 및 클라이언트 기능에 따라 다음 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="acd99-132">**PIN 인증 사용** - PIN 번호를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="acd99-133">**인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="acd99-134">**인증서 체인 다운로드 사용** - 인증 인증서가 있는 서버에서 해당 인증서에 대해 인증서 체인을 다운로드하도록 합니다</span><span class="sxs-lookup"><span data-stu-id="acd99-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="acd99-135">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="acd99-136">기존 웹 서비스 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="acd99-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="acd99-137">다음 단계에 따라 웹 서비스 구성 설정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="acd99-138">웹 서비스 구성 설정을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="acd99-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="acd99-139">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="acd99-140">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="acd99-141">왼쪽 탐색 표시줄에서 **보안**, **웹 서비스** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="acd99-142">**웹 서비스** 페이지의 검색 필드에 삭제할 정책의 이름 일부나 전체를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="acd99-143">정책 목록에서 원하는 정책을 클릭하고 **편집** 을 클릭한 다음 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="acd99-144">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="acd99-145">Cmdlet을 사용하여 웹 Windows PowerShell 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="acd99-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="acd99-146">웹 서비스 구성 설정은 **Remove-CsWebServiceConfiguration** cmdlet을 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="acd99-147">비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="acd99-148">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acd99-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="acd99-149">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="acd99-150">웹 서비스 구성 설정의 특정 컬렉션을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="acd99-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="acd99-151">다음 명령은 Redmond 사이트에 적용된 웹 서비스 보안 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="acd99-152">사이트 범위에 적용된 모든 웹 서비스 구성 설정을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="acd99-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="acd99-153">다음 명령은 서비스 범위에 적용된 모든 웹 서비스 보안 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="acd99-154">인증서 인증을 허용하는 모든 웹 서비스 구성 설정을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="acd99-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="acd99-155">다음 명령은 인증서 인증을 사용할 수 있도록 허용하는 모든 웹 서비스 보안 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="acd99-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="acd99-156">자세한 내용은 [Remove-CsWebServiceConfiguration을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="acd99-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

