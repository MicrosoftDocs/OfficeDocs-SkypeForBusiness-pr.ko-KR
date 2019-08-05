---
title: 비즈니스용 Skype 서버에서 웹 서비스 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '요약: 비즈니스용 Skype 서버에서 웹 서비스 구성 설정을 관리 합니다.'
ms.openlocfilehash: b2a7f287c9386c89d132e03e96aa25e9472f7008
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196898"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="743fc-103">비즈니스용 Skype 서버에서 웹 서비스 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="743fc-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="743fc-104">**요약:** 비즈니스용 Skype 서버의 웹 서비스 구성 설정을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="743fc-105">**웹 서비스** 페이지를 사용 하 여 비즈니스용 Skype 서버 관련 웹 서버 및 웹 서비스에 액세스 하는 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="743fc-106">새 웹 서비스 정책을 만들려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="743fc-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="743fc-107">새 웹 서비스 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="743fc-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="743fc-108">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="743fc-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="743fc-109">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="743fc-110">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **웹 서비스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="743fc-111">**웹 서비스** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="743fc-112">사이트에 대 한 웹 서비스를 구성 하려면 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="743fc-113">**사이트 선택**에서 웹 서비스 정책이 사이트를 적용 하는 사이트를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="743fc-114">풀에 대 한 웹 서비스를 구성 하려면 **풀 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="743fc-115">**서비스 선택**에서 웹 서비스 정책이 적용 되는 서비스를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="743fc-116">**새 웹 서비스 설정**에서 **windows 통합 인증**에서 **협상**, **windows 통합 인증**또는 **없음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="743fc-117">해당 환경의 클라이언트 및 지원 기능에 따라 다음 중 하나 이상을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="743fc-118">Pin **인증** 을 사용 하 여 클라이언트가 pin 번호를 사용 하 여 인증할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="743fc-119">**인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="743fc-120">**인증서 체인 다운로드 사용** 인증 인증서를 사용 하 여 서버에 제공 되는 경우 해당 인증서의 인증서 체인을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="743fc-121">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="743fc-122">기존 웹 서비스 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="743fc-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="743fc-123">**웹 서비스** 페이지를 사용 하 여 비즈니스용 Skype 서버 관련 웹 서버 및 웹 서비스에 액세스 하는 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="743fc-124">기존 웹 서비스 정책을 수정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="743fc-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="743fc-125">기존 웹 서비스 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="743fc-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="743fc-126">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="743fc-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="743fc-127">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="743fc-128">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **웹 서비스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="743fc-129">**웹 서비스** 페이지에서 구성을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="743fc-130">**웹 서비스 편집 설정**의 **Windows 통합 인증**에서 **협상**, **windows 통합 인증**또는 **없음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="743fc-131">해당 환경의 클라이언트 및 지원 기능에 따라 다음 중 하나 이상을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="743fc-132">Pin **인증** 을 사용 하 여 클라이언트가 pin 번호를 사용 하 여 인증할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="743fc-133">**인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="743fc-134">**인증서 체인 다운로드 사용** 인증 인증서를 사용 하 여 서버에 제공 되는 경우 해당 인증서의 인증서 체인을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="743fc-135">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="743fc-136">기존 웹 서비스 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="743fc-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="743fc-137">웹 서비스 구성 설정을 삭제 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="743fc-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="743fc-138">웹 서비스 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="743fc-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="743fc-139">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="743fc-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="743fc-140">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="743fc-141">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **웹 서비스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="743fc-142">**웹 서비스** 페이지의 검색 필드에 삭제 하려는 정책의 이름 전체 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="743fc-143">정책 목록에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="743fc-144">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="743fc-145">Windows PowerShell Cmdlet을 사용 하 여 웹 서비스 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="743fc-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="743fc-146">Windows PowerShell 및 **Remove CsWebServiceConfiguration** cmdlet을 사용 하 여 웹 서비스 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="743fc-147">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="743fc-148">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="743fc-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="743fc-149">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="743fc-150">웹 서비스 구성 설정의 특정 컬렉션을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="743fc-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="743fc-151">다음 명령은 Redmond 사이트에 적용 된 웹 서비스 보안 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="743fc-152">사이트 범위에 적용 된 모든 웹 서비스 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="743fc-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="743fc-153">다음 명령은 서비스 범위에 적용 된 모든 웹 서비스 보안 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="743fc-154">인증서 인증을 허용 하는 모든 웹 서비스 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="743fc-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="743fc-155">다음 명령은 인증서 인증을 사용할 수 있는 모든 웹 서비스 보안 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="743fc-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="743fc-156">자세한 내용은 [제거-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="743fc-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

