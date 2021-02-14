---
title: 호출 데이터 커넥터 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype Online 도구를 사용하여 비즈니스용 Skype의 원격 분석이 볼 수 있도록 하는 통화 데이터 커넥터를 구성하기 위한 지침입니다.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726928"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="b1942-103">호출 데이터 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="b1942-103">Configure Call Data Connector</span></span>

<span data-ttu-id="b1942-104">이 문서에서는 비즈니스용 Skype 온라인 통화 품질 대시보드(CQD) 및 CA(통화 분석) 도구를 사용하여 비즈니스용 Skype 서버 통화 품질 데이터를 볼 수 있도록 하는 단일 도구 집합인 통화 데이터 커넥터를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="b1942-105">역할 요구 사항 및 하이브리드 연결 설정과 같은 통화 데이터 커넥터의 이점 및 선행 조건에 대한 자세한 내용은 통화 데이터 커넥터 [계획(Plan Call Data Connector)을 참조하십시오.](plan-call-data-connector.md)</span><span class="sxs-lookup"><span data-stu-id="b1942-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="b1942-106">모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="b1942-106">Enable Monitoring</span></span>
 
<span data-ttu-id="b1942-107">로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용하여 프런트 엔드 풀 모니터링에서 CDR(통화 데이터 기록) 및 QoE(QoE) 데이터 수집을 구성해야 합니다. 그렇지 않으면 통화 분석 및 통화 품질 대시보드에서 사용할 데이터를 얻지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="b1942-108">통화 데이터 커넥터를 구성하기 전에 비즈니스용 [Skype](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 서버에서 모니터링 배포에 제공된 단계에 따라 CDR 및 QoE와 기본 모니터링을 모두 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1942-109">프런트 엔드 풀에서 모니터링을 사용하도록 설정하지 않은 경우 통화 데이터 커넥터가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="b1942-110">통화 데이터 커넥터 사용</span><span class="sxs-lookup"><span data-stu-id="b1942-110">Enable Call Data Connector</span></span>

<span data-ttu-id="b1942-111">통화 데이터 커넥터를 구성하고 사용하도록 설정하려면 다음 cmdlet을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="b1942-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b1942-112">Cmdlet</span></span>| <span data-ttu-id="b1942-113">설명</span><span class="sxs-lookup"><span data-stu-id="b1942-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="b1942-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="b1942-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="b1942-115">온라인 데이터 수집을 설정하는 온라인 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="b1942-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="b1942-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="b1942-117">기존 온라인 데이터 수집기에서 검색하는 온라인 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="b1942-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="b1942-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="b1942-119">프레미스 cmdlet에서 만든 연결 정보를 검색하는 New-CsCloudCallDataConnection cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="b1942-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="b1942-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="b1942-121">프레미스 cmdlet에서 만든 연결 정보의 New-CsCloudCallDataConnection 저장하는 New-CsCloudCallDataConnection cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="b1942-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1942-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="b1942-123">커넥터를 활성화 또는 사용하지 않도록 설정하고 범위 수준을 사용자 지정할 수 있는 On-프레미스 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="b1942-124">구성을 지우고 다시 시작하려면 Remove-csclouddatconnectorconfiguration cmdlet을 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="b1942-125">환경 구성</span><span class="sxs-lookup"><span data-stu-id="b1942-125">Configure your environment</span></span> 

<span data-ttu-id="b1942-126">온라인 데이터 수집을 사용하도록 환경을 구성하려면 먼저 비즈니스용 Skype Online PowerShell에 관리자로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="b1942-127">자세한 내용은 [Office 365 PowerShell을](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)사용하여 비즈니스용 Skype Online 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1942-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="b1942-128">비즈니스용 Skype Online PowerShell에 로그인하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="b1942-129">비즈니스용 Skype 서버 2019 관리 셸에서(권장 방법)</span><span class="sxs-lookup"><span data-stu-id="b1942-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="b1942-130">다른 PowerShell 세션에서</span><span class="sxs-lookup"><span data-stu-id="b1942-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="b1942-131">비즈니스용 Skype 서버 관리 셸에서 비즈니스용 Skype Online PowerShell에 로그인(권장 방법)</span><span class="sxs-lookup"><span data-stu-id="b1942-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="b1942-132">커넥터를 처음으로 사용하도록 설정하는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="b1942-133">연결이 이미 있는 경우 테넌트에 대한 통화 데이터 연결이 이미 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="b1942-134">이 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="b1942-135">다른 PowerShell 세션에서 비즈니스용 Skype Online PowerShell에 로그인합니다(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="b1942-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="b1942-136">커넥터를 처음으로 사용하도록 설정하는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="b1942-137">연결이 이미 있는 경우 테넌트에 대한 통화 데이터 연결이 이미 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="b1942-138">이 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="b1942-139">위의 명령의 출력에는 다음과 같이 토큰 값이 포함되어 있으며, 이 토큰 값은 다음과 같이 프레미스 환경을 구성할 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="b1942-140">비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="b1942-141">범위 구성</span><span class="sxs-lookup"><span data-stu-id="b1942-141">Configure the scope</span></span>

<span data-ttu-id="b1942-142">비즈니스용 Skype 서버 관리 셸 내에서 Set-CsCloudCallDataConnectorConfiguration cmdlet을 사용하여 특정 사이트 또는 전체 비즈니스용 Skype 서버 배포에 대해 통화 데이터 커넥터를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="b1942-143">예를 들어 다음 명령은 전역 범위에서 Call Data Connector를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="b1942-144">전역 설정 외에도 통화 데이터 커넥터 구성 설정을 사이트 범위에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="b1942-145">따라서 모니터링과 관련해 추가적인 관리 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="b1942-146">예를 들어 관리자는 다음 예와 같이 Redmond 사이트에 대해 통화 데이터 커넥터 전달을 사용하도록 설정하고 Dublin 사이트에 대해 통화 데이터 커넥터 전달을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="b1942-147">사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="b1942-148">예를 들어 Call Data Connector 전달이 전역 범위에서 사용되지만 사이트 범위(Redmond 사이트의 경우)에서 사용하지 않도록 설정되어 있는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="b1942-149">즉, Redmond 사이트의 사용자에게 통화 정보 기록 및 QoE 정보가 전달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="b1942-150">그러나 다른 사이트의 사용자(즉, Redmond 사이트 설정 대신 전역 설정으로 관리되는 사용자)는 통화 정보 기록 및 QoE 정보를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="b1942-151">통화 데이터 커넥터에서 사용하는 가장 일반적으로 사용되는 설정의 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="b1942-152">속성</span><span class="sxs-lookup"><span data-stu-id="b1942-152">Property</span></span>|<span data-ttu-id="b1942-153">설명</span><span class="sxs-lookup"><span data-stu-id="b1942-153">Description</span></span>|<span data-ttu-id="b1942-154">기본값</span><span class="sxs-lookup"><span data-stu-id="b1942-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b1942-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="b1942-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="b1942-156">통화 데이터 커넥터를 사용할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="b1942-157">True로 설정하면 모니터링 레코드가 온라인 모니터링으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="b1942-158">$False</span><span class="sxs-lookup"><span data-stu-id="b1942-158">$False</span></span>  <br/> |
| <span data-ttu-id="b1942-159">ID</span><span class="sxs-lookup"><span data-stu-id="b1942-159">Identity</span></span> | <span data-ttu-id="b1942-160">명령의 범위 수준(전역 또는 사이트)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="b1942-161">global</span><span class="sxs-lookup"><span data-stu-id="b1942-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="b1942-162">통화 데이터 커넥터를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="b1942-162">Disable Call Data Connector</span></span>

<span data-ttu-id="b1942-163">통화 데이터 커넥터를 설정하지 않으면 프런트 엔드 풀에서 모니터링 저장소의 연결이 되거나 백 엔드 모니터링 데이터베이스에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="b1942-164">통화 데이터 커넥터를 사용하지 않도록 설정하면 비즈니스용 Skype 서버가 클라우드에 통화 데이터를 업로드하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="b1942-165">비즈니스용 Skype 서버 관리 셸 내에서 Set-CsCloudCallDataConnectorConfiguration cmdlet을 사용하여 Call Data Connector를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="b1942-166">예를 들어 다음 명령은 EnableCallDataConnector 속성을 기본 설정으로 설정하여 전역 범위에서 Call Data Connector를 $False.</span><span class="sxs-lookup"><span data-stu-id="b1942-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="b1942-167">클라우드에 통화 데이터 업로드를 다시 시작하려면 다음 예제와 같이 EnableCallDataConnector 속성을 $True 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1942-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="b1942-168">온라인 대시보드를 통해온-프레미스 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="b1942-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="b1942-169">통화 데이터 커넥터를 사용하도록 설정한 후 통화 분석을 사용하여 품질 불량 문제를 해결하고 [](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) Microsoft Teams 및 비즈니스용 [Skype Online에](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)대해 통화 품질 대시보드를 켜고 사용하는 설명에 따라 통화 분석 대시보드 또는 통화 품질 대시보드에서온-프레미스 통화 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b1942-170">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="b1942-170">For more information</span></span>

<span data-ttu-id="b1942-171">cmdlet에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸에서 Get-Help 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1942-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b1942-172">예시:</span><span class="sxs-lookup"><span data-stu-id="b1942-172">For example:</span></span>

<span data-ttu-id="b1942-173">Get-Help Get-CsCloudCallDataConnector | more</span><span class="sxs-lookup"><span data-stu-id="b1942-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="b1942-174">Get-Help Set-CsCloudCallDataConnector | more</span><span class="sxs-lookup"><span data-stu-id="b1942-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="b1942-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span><span class="sxs-lookup"><span data-stu-id="b1942-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
