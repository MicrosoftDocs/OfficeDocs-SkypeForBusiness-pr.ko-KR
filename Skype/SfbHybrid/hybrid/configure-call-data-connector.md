---
title: 통화 데이터 커넥터 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype Online 도구를 사용 하 여 온-프레미스로 원격 분석을 볼 수 있도록 하는 Call Data Connector 구성에 대 한 지침입니다.
ms.openlocfilehash: 48af644523e9872107c814aa330d2af2d9a4272f
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328377"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="516b3-103">통화 데이터 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="516b3-103">Configure Call Data Connector</span></span>

<span data-ttu-id="516b3-104">이 문서에서는 비즈니스용 Skype Online for CQD (온라인 통화 품질 대시보드) 및 CA (전화 분석) 도구를 사용 하 여 비즈니스용 Skype 서버 통화 품질 데이터를 볼 수 있는 단일 도구 집합 인 Call Data Connector를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="516b3-105">통화 데이터 커넥터 혜택 및 역할 요구 사항, 하이브리드 연결 설정 등의 필수 구성 요소에 대 한 자세한 내용은 [요금제 호출 데이터 커넥터](plan-call-data-connector.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="516b3-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="516b3-106">모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="516b3-106">Enable Monitoring</span></span>
 
<span data-ttu-id="516b3-107">프론트 엔드 풀 모니터링에서 로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용 하 여 체감 품질 (Call Data 레코딩) 및 체험 (환경 품질) 데이터 수집을 구성 해야 합니다. 그렇지 않으면 통화 분석 및 통화 품질 대시보드에서 작업할 데이터를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="516b3-108">통화 데이터 커넥터를 구성 하기 전에 [비즈니스용 Skype 서버에서 모니터링 배포](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 에 제공 되는 단계를 따라 CDR 및 체감 품질 및 기본 모니터링을 모두 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="516b3-109">프런트 엔드 풀에서 모니터링을 사용할 수 없는 경우에는 Call Data Connector가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="516b3-110">Call Data Connector 사용</span><span class="sxs-lookup"><span data-stu-id="516b3-110">Enable Call Data Connector</span></span>

<span data-ttu-id="516b3-111">Call Data Connector를 구성 하 고 사용 하도록 설정 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="516b3-112">은</span><span class="sxs-lookup"><span data-stu-id="516b3-112">Cmdlet</span></span>| <span data-ttu-id="516b3-113">설명</span><span class="sxs-lookup"><span data-stu-id="516b3-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="516b3-114">새로운 CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="516b3-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="516b3-115">온라인 데이터 수집기를 설정 하는 온라인 cmdlet.</span><span class="sxs-lookup"><span data-stu-id="516b3-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="516b3-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="516b3-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="516b3-117">기존 온라인 데이터 수집기를 검색 하는 온라인 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="516b3-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="516b3-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="516b3-119">CsCloudCallDataConnection cmdlet에서 만든 연결 정보를 검색 하는 온-프레미스 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="516b3-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="516b3-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="516b3-121">CsCloudCallDataConnection cmdlet에서 만든 연결 정보의 온-프레미스 복사본을 저장 하는 온-프레미스 cmdlet.</span><span class="sxs-lookup"><span data-stu-id="516b3-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="516b3-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="516b3-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="516b3-123">커넥터를 사용 하거나 사용 하지 않도록 설정 하 고 범위 수준을 사용자 지정할 수 있는 온-프레미스 cmdlet.</span><span class="sxs-lookup"><span data-stu-id="516b3-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="516b3-124">구성을 지우고 다시 시작 하려면 제거-csclouddat연결할 구성 cmdlet을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="516b3-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="516b3-125">환경 구성</span><span class="sxs-lookup"><span data-stu-id="516b3-125">Configure your environment</span></span> 

<span data-ttu-id="516b3-126">온라인 데이터 수집기를 사용 하도록 환경을 구성 하려면 먼저 비즈니스용 Skype Online PowerShell에 관리자로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="516b3-127">자세한 내용은 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="516b3-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="516b3-128">비즈니스용 Skype Online PowerShell에 로그인 하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="516b3-129">비즈니스용 Skype 서버 2019 관리 셸에서 (권장 방법)</span><span class="sxs-lookup"><span data-stu-id="516b3-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="516b3-130">다른 PowerShell 세션에서</span><span class="sxs-lookup"><span data-stu-id="516b3-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="516b3-131">비즈니스용 Skype 서버 관리 셸에서 비즈니스용 Skype Online PowerShell에 로그인 (권장 방법)</span><span class="sxs-lookup"><span data-stu-id="516b3-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="516b3-132">커넥터를 처음 사용 하는 경우 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-132">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="516b3-133">연결이 이미 존재 한다는 오류가 표시 되 면 테 넌 트에 대 한 통화 데이터 연결이 이미 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="516b3-134">이 경우 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-134">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="516b3-135">다른 PowerShell 세션에서 비즈니스용 Skype Online PowerShell에 로그인 (선택 방법)</span><span class="sxs-lookup"><span data-stu-id="516b3-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="516b3-136">커넥터를 처음 사용 하는 경우 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-136">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="516b3-137">연결이 이미 존재 한다는 오류가 표시 되 면 테 넌 트에 대 한 통화 데이터 연결이 이미 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="516b3-138">이 경우 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-138">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="516b3-139">위의 명령 출력에는 온-프레미스 환경을 다음과 같이 구성할 때 필요한 토큰 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="516b3-140">비즈니스용 Skype 서버 관리 셸에서는 다음 명령을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="516b3-141">범위 구성</span><span class="sxs-lookup"><span data-stu-id="516b3-141">Configure the scope</span></span>

<span data-ttu-id="516b3-142">비즈니스용 Skype 서버 관리 셸에서 CsCloudCallDataConnectorConfiguration cmdlet을 사용 하 여 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대 한 통화 데이터 커넥터를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="516b3-143">예를 들어 다음 명령은 전역 범위에서 Call 데이터 커넥터를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="516b3-144">전역 설정 외에도, 통화 데이터 커넥터 구성 설정을 사이트 범위에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="516b3-145">이렇게 하면 모니터링할 때 추가적으로 관리 유연성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="516b3-146">예를 들어 관리자는 다음 예제와 같이 Redmond 사이트에 대 한 통화 데이터 커넥터 전달을 활성화할 수 있지만, 더블린 사이트에 대 한 Call Data 커넥터 전달은 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="516b3-147">사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="516b3-148">예를 들어 통화 데이터 커넥터 전달은 전역 범위에서 사용 하도록 설정 되어 있지만 사이트 범위 (Redmond 사이트의 경우)에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="516b3-149">이는 Redmond 사이트의 사용자에 대해 통화 정보 기록 및 체감 품질 정보를 전달 하지 않는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="516b3-150">그러나 다른 사이트 (즉, Redmond 사이트 설정 대신 전역 설정으로 관리 되는 사용자)의 사용자에 게는 통화 정보 기록 및 체감 품질 정보가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="516b3-151">Call 데이터 커넥터에서 사용 하는 가장 일반적으로 사용 되는 설정 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="516b3-152">속성</span><span class="sxs-lookup"><span data-stu-id="516b3-152">Property</span></span>|<span data-ttu-id="516b3-153">설명</span><span class="sxs-lookup"><span data-stu-id="516b3-153">Description</span></span>|<span data-ttu-id="516b3-154">기본값</span><span class="sxs-lookup"><span data-stu-id="516b3-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="516b3-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="516b3-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="516b3-156">Call Data 커넥터를 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="516b3-157">True 인 경우 모니터링 레코드는 온라인 모니터링으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="516b3-158">$False</span><span class="sxs-lookup"><span data-stu-id="516b3-158">$False</span></span>  <br/> |
| <span data-ttu-id="516b3-159">Identity</span><span class="sxs-lookup"><span data-stu-id="516b3-159">Identity</span></span> | <span data-ttu-id="516b3-160">명령에 대 한 범위 수준을 전역 또는 사이트 중에서 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="516b3-161">전체적</span><span class="sxs-lookup"><span data-stu-id="516b3-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="516b3-162">Call Data Connector 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="516b3-162">Disable Call Data Connector</span></span>

<span data-ttu-id="516b3-163">Call Data Connector를 사용 하지 않도록 설정 하면 프런트 엔드 풀의 모니터링 저장소는 연결 되지 않으며, 백엔드 모니터링 데이터베이스에 대 한 제거 또는 다른 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="516b3-164">통화 데이터 커넥터를 사용 하지 않도록 설정 하면 비즈니스용 Skype 서버가 클라우드에 대 한 통화 데이터를 업로드 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="516b3-165">비즈니스용 Skype Server management shell 내에서 CsCloudCallDataConnectorConfiguration cmdlet을 사용 하 여 통화 데이터 커넥터를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="516b3-166">예를 들어 다음 명령은 EnableCallDataConnector 속성을 $False로 설정 하 여 전역 범위에서 Call 데이터 커넥터를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="516b3-167">클라우드에 통화 데이터 업로드를 다시 시작 하려면 다음 예제와 같이 EnableCallDataConnector 속성을 다시 $True으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="516b3-168">온라인 대시보드를 통해 온-프레미스 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="516b3-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="516b3-169">통화 데이터 커넥터를 사용 하도록 설정한 후에는 통화 분석 대시보드에서의 온-프레미스 호출 데이터를 사용 하 여 콜 분석 대시보드의 통화 품질 대시보드에서 [문제 해결](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 에 대 한 자세한 음질을 확인 하 고 [통화 품질 대시보드를 켜고 사용할 수 있습니다. Microsoft 팀 및 비즈니스용 Skype Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="516b3-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="516b3-170">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="516b3-170">For more information</span></span>

<span data-ttu-id="516b3-171">Cmdlet에 대 한 자세한 내용은 비즈니스용 Skype 서버 관리 셸에서의 Get-help-Help 명령을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="516b3-172">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="516b3-172">For example:</span></span>

<span data-ttu-id="516b3-173">Get-help 가져오기-CsCloudCallDataConnector | 자세한</span><span class="sxs-lookup"><span data-stu-id="516b3-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="516b3-174">Get-help 설정-CsCloudCallDataConnector | 자세한</span><span class="sxs-lookup"><span data-stu-id="516b3-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="516b3-175">Get-help 설정-CsCloudCallDataConnectorConfiguration | 자세한</span><span class="sxs-lookup"><span data-stu-id="516b3-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
