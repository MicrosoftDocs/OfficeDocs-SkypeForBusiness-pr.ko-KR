---
title: Call Data Connector 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype Online 도구를 사용 하 여 온-프레미스에서 비즈니스용의 원격 분석을 볼 수 있도록 하는 Call Data Connector를 구성 하기 위한 지침입니다.
ms.openlocfilehash: 4d472ce49a3059df7286c647b013abe321b9fd15
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963046"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="8ec2e-103">Call Data Connector 구성</span><span class="sxs-lookup"><span data-stu-id="8ec2e-103">Configure Call Data Connector</span></span>

<span data-ttu-id="8ec2e-104">이 문서에서는 Skype for Business 온라인 통화 품질 대시보드 (CQD) 및 CA (통화 분석) 도구를 사용 하 여 비즈니스용 Skype 서버 통화 품질 데이터를 볼 수 있도록 하는 단일 도구 집합이 있는 Call Data Connector를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="8ec2e-105">통화 데이터 커넥터 이점과 필수 구성 요소 (예: 역할 요구 사항 및 하이브리드 연결 설정)에 대 한 자세한 내용은 [Plan Call Data Connector](plan-call-data-connector.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="8ec2e-106">모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="8ec2e-106">Enable Monitoring</span></span>
 
<span data-ttu-id="8ec2e-107">QoE (Call Data 레코딩) 및 프런트 엔드 풀 모니터링에서 로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용 하 여 데이터 수집을 구성 해야 합니다. 그렇지 않으면 통화 분석 및 통화 품질 대시보드가 작업할 데이터를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="8ec2e-108">통화 데이터 커넥터를 구성 하기 전에 [비즈니스용 Skype 서버의 배포 모니터링](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 에서 제공 되는 단계에 따라 CDR 및 QoE를 비롯 하 여 기본 모니터링을 모두 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ec2e-109">프런트 엔드 풀에서 모니터링을 사용 하지 않는 경우에는 Call Data Connector가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="8ec2e-110">Call Data Connector 사용</span><span class="sxs-lookup"><span data-stu-id="8ec2e-110">Enable Call Data Connector</span></span>

<span data-ttu-id="8ec2e-111">Call Data Connector를 구성 하 고 사용 하도록 설정 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="8ec2e-112">#A0</span><span class="sxs-lookup"><span data-stu-id="8ec2e-112">Cmdlet</span></span>| <span data-ttu-id="8ec2e-113">설명</span><span class="sxs-lookup"><span data-stu-id="8ec2e-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="8ec2e-114">CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="8ec2e-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="8ec2e-115">온라인 데이터 수집기를 설정 하는 온라인 cmdlet</span><span class="sxs-lookup"><span data-stu-id="8ec2e-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="8ec2e-116">CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="8ec2e-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="8ec2e-117">기존 온라인 데이터 수집기를 검색 하는 온라인 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="8ec2e-118">CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="8ec2e-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="8ec2e-119">CsCloudCallDataConnection cmdlet을 사용 하 여 만든 연결 정보를 검색 하는 온-프레미스 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="8ec2e-120">CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="8ec2e-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="8ec2e-121">CsCloudCallDataConnection cmdlet을 사용 하 여 만든 연결 정보의 온-프레미스 복사본을 저장 하는 온-프레미스 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="8ec2e-122">CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ec2e-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="8ec2e-123">커넥터를 사용 하거나 사용 하지 않도록 설정 하 고 범위 수준을 사용자 지정할 수 있는 온-프레미스 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="8ec2e-124">구성을 지우고 다시 시작 하려면 Remove-csclouddat커넥터 구성 cmdlet을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="8ec2e-125">환경 구성</span><span class="sxs-lookup"><span data-stu-id="8ec2e-125">Configure your environment</span></span> 

<span data-ttu-id="8ec2e-126">온라인 데이터 수집기를 사용 하도록 환경을 구성 하려면 먼저 비즈니스용 Skype Online PowerShell에 관리자로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="8ec2e-127">자세한 내용은 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="8ec2e-128">비즈니스용 Skype Online PowerShell에 로그인 하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="8ec2e-129">비즈니스용 Skype 서버 2019 관리 셸 (권장 방법)</span><span class="sxs-lookup"><span data-stu-id="8ec2e-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="8ec2e-130">다른 PowerShell 세션에서</span><span class="sxs-lookup"><span data-stu-id="8ec2e-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="8ec2e-131">비즈니스용 skype 서버 관리 셸에서 비즈니스용 Skype Online PowerShell에 로그인 합니다 (권장 방법).</span><span class="sxs-lookup"><span data-stu-id="8ec2e-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="8ec2e-132">처음으로 커넥터를 사용 하도록 설정 하는 경우 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="8ec2e-133">연결이 이미 존재 한다는 오류가 표시 되 면 테 넌 트에 대 한 호출 데이터 연결이 이미 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="8ec2e-134">이 경우에는 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="8ec2e-135">다른 PowerShell 세션에서 비즈니스용 Skype Online PowerShell에 로그인 (optional 메서드)</span><span class="sxs-lookup"><span data-stu-id="8ec2e-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="8ec2e-136">처음으로 커넥터를 사용 하도록 설정 하는 경우 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="8ec2e-137">연결이 이미 존재 한다는 오류가 표시 되 면 테 넌 트에 대 한 호출 데이터 연결이 이미 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="8ec2e-138">이 경우에는 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="8ec2e-139">위의 명령 출력에는 다음과 같이 온-프레미스 환경을 구성할 때 필요한 토큰 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="8ec2e-140">비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="8ec2e-141">범위 구성</span><span class="sxs-lookup"><span data-stu-id="8ec2e-141">Configure the scope</span></span>

<span data-ttu-id="8ec2e-142">비즈니스용 Skype 서버 관리 셸에서 CsCloudCallDataConnectorConfiguration cmdlet을 사용 하 여 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대해 Call Data Connector를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="8ec2e-143">예를 들어 다음 명령은 전역 범위에서 Call Data Connector를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="8ec2e-144">전역 설정 외에도, 통화 데이터 커넥터 구성 설정이 사이트 범위에 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="8ec2e-145">이렇게 하면 모니터링에 있어 추가 관리 유연성이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="8ec2e-146">예를 들어 관리자가 Redmond 사이트에 대 한 통화 데이터 커넥터 전달을 사용 하도록 설정할 수 있지만 다음 예제와 같이 더블린 사이트에 대 한 통화 데이터 커넥터 전달을 사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="8ec2e-147">사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="8ec2e-148">예를 들어 Call Data Connector 전달은 전역 범위에서 사용 하도록 설정 되어 있지만 사이트 범위에서 사용 하지 않도록 설정 되어 있습니다 (Redmond 사이트의 경우).</span><span class="sxs-lookup"><span data-stu-id="8ec2e-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="8ec2e-149">즉, Redmond 사이트의 사용자에 대해 통화 정보 기록 및 QoE 정보가 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="8ec2e-150">그러나 다른 사이트의 사용자, 즉 Redmond 사이트 설정 대신 전역 설정으로 관리 되는 사용자에 게는 통화 정보 기록 및 QoE 정보가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="8ec2e-151">Call Data Connector에서 사용 되는 가장 일반적으로 사용 되는 설정 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="8ec2e-152">속성</span><span class="sxs-lookup"><span data-stu-id="8ec2e-152">Property</span></span>|<span data-ttu-id="8ec2e-153">설명</span><span class="sxs-lookup"><span data-stu-id="8ec2e-153">Description</span></span>|<span data-ttu-id="8ec2e-154">기본값</span><span class="sxs-lookup"><span data-stu-id="8ec2e-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ec2e-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="8ec2e-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="8ec2e-156">Call Data Connector가 사용 하도록 설정 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="8ec2e-157">True 인 경우 모니터링 레코드가 온라인 모니터링으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="8ec2e-158">$False</span><span class="sxs-lookup"><span data-stu-id="8ec2e-158">$False</span></span>  <br/> |
| <span data-ttu-id="8ec2e-159">ID</span><span class="sxs-lookup"><span data-stu-id="8ec2e-159">Identity</span></span> | <span data-ttu-id="8ec2e-160">명령의 범위 수준 (전역 또는 사이트)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="8ec2e-161">global</span><span class="sxs-lookup"><span data-stu-id="8ec2e-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="8ec2e-162">Call Data Connector 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="8ec2e-162">Disable Call Data Connector</span></span>

<span data-ttu-id="8ec2e-163">Call Data Connector를 사용 하지 않도록 설정 해도 프런트 엔드 풀에서 모니터링 저장소의 연결이 해제 되지 않으며 백엔드 모니터링 데이터베이스도 제거 되거나 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="8ec2e-164">통화 데이터 커넥터를 사용 하지 않도록 설정 하면 비즈니스용 Skype 서버가 클라우드로 호출 데이터를 업로드 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="8ec2e-165">비즈니스용 Skype 서버 관리 셸에서 CsCloudCallDataConnectorConfiguration cmdlet을 사용 하 여 Call Data Connector를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="8ec2e-166">예를 들어 다음 명령은 EnableCallDataConnector 속성을 $False로 설정 하 여 전역 범위에서 Call Data Connector를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="8ec2e-167">클라우드로의 통화 데이터 업로드를 다시 시작 하려면 다음 예제와 같이 EnableCallDataConnector 속성을 다시 $True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="8ec2e-168">온라인 대시보드를 통해 온-프레미스 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="8ec2e-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="8ec2e-169">Call Data Connector를 사용 하도록 설정한 후에는 통화 분석 대시보드에서 통화 품질 대시보드의 온-프레미스 통화 데이터를 확인 [하 여 사용 중인 품질 문제를 해결 하](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 고 [Microsoft 팀 및 비즈니스용 Skype Online에 대 한 통화 품질 대시보드를 켜고 사용할](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="8ec2e-170">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="8ec2e-170">For more information</span></span>

<span data-ttu-id="8ec2e-171">Cmdlet에 대 한 자세한 내용은 비즈니스용 Skype 서버 관리 셸에서 Get-Help 명령을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8ec2e-172">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec2e-172">For example:</span></span>

<span data-ttu-id="8ec2e-173">Get-help-CsCloudCallDataConnector | 자세한</span><span class="sxs-lookup"><span data-stu-id="8ec2e-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="8ec2e-174">Get-help CsCloudCallDataConnector | 자세한</span><span class="sxs-lookup"><span data-stu-id="8ec2e-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="8ec2e-175">Get-help CsCloudCallDataConnectorConfiguration | 자세한</span><span class="sxs-lookup"><span data-stu-id="8ec2e-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
