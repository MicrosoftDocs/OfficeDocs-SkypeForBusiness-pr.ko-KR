---
title: Microsoft Teams 디바이스 모니터링 및 경고
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 Teams 모니터링 및 경고 기능을 사용하여 Teams 디바이스의 상태 상태를 사전 모니터링하는 방법에 대해 자세히 알아보기
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 03a57da7af783fa95e0bccbcb6a96f183b2fbb90
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819501"
---
# <a name="microsoft-teams-device-health-monitoring"></a><span data-ttu-id="d5d63-103">Microsoft Teams 디바이스 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="d5d63-103">Microsoft Teams device health monitoring</span></span>

<span data-ttu-id="d5d63-104">Microsoft Teams 관리 센터의 디바이스 상태 모니터링을 사용하면 다양한 Teams 디바이스의 상태도 사전 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-104">Device health monitoring in the Microsoft Teams admin center gives you an ability to proactively monitor the health of various Teams devices.</span></span> <span data-ttu-id="d5d63-105">조직의 모니터링된 디바이스가 오프라인 상태가면 디바이스의 오프라인 상태를 모니터링하고 실시간으로 경고를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-105">Monitor the offline state of a device and receive alerts in real time if the monitored device in your organization goes offline.</span></span>  

<span data-ttu-id="d5d63-106">시작하기 전에 테넌트에 팀/채널 만들기 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-106">Before you start, you'll need the teams/channel creation permissions in your tenant.</span></span> <span data-ttu-id="d5d63-107">[자세히 알아보기 를 자세히 알아보자.](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="d5d63-107">[Learn More](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).</span></span>

## <a name="configure-device-state-rule"></a><span data-ttu-id="d5d63-108">디바이스 상태 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="d5d63-108">Configure device state rule</span></span>

1. <span data-ttu-id="d5d63-109">Microsoft Teams 관리 센터의 왼쪽 탐색에서 알림 & 규칙 **을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d5d63-109">In the left navigation of the Microsoft Teams admin center, select **Notifications & alerts** > **Rules**.</span></span>

   ![관리 센터의 규칙 섹션](../media/select-rules.png)

2. <span data-ttu-id="d5d63-111">규칙 **페이지에서** 디바이스 **상태 규칙 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d5d63-111">In the **Rules** Page, select **Device state rule**.</span></span>

3. <span data-ttu-id="d5d63-112">디바이스를 선택하여 경고를 사용하도록 설정하기 위한 상태 규칙을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-112">Select the device to configure the state rule for enabling alerts.</span></span>

    ![Teams 디바이스 상태 규칙 페이지입니다.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a><span data-ttu-id="d5d63-114">규칙 구성 해석</span><span class="sxs-lookup"><span data-stu-id="d5d63-114">Interpret the rule configuration</span></span>


|<span data-ttu-id="d5d63-115">필드</span><span class="sxs-lookup"><span data-stu-id="d5d63-115">Field</span></span> |<span data-ttu-id="d5d63-116">설명</span><span class="sxs-lookup"><span data-stu-id="d5d63-116">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="d5d63-117">**규칙 형식**</span><span class="sxs-lookup"><span data-stu-id="d5d63-117">**Rule type**</span></span>   |<span data-ttu-id="d5d63-118">디바이스 상태 규칙을 사용하면 효과적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-118">The device state rule helps you effectively manage.</span></span> <span data-ttu-id="d5d63-119">Teams 디바이스 및 디바이스 관리 유형으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-119">Teams devices and is classified as a device management type.</span></span> <span data-ttu-id="d5d63-120">향후에는 다른 관련 기능을 모니터링할 수 있도록 디바이스 관리 유형의 더 많은 규칙을 사용할 수 있습니다(예: 부적정한 디바이스 및 디바이스의 로그인 상태 포함).</span><span class="sxs-lookup"><span data-stu-id="d5d63-120">In the future, more rules of device management type will be available to monitor other related capabilities (examples may include: unhealthy device and the sign-in status of device).</span></span>|
|<span data-ttu-id="d5d63-121">**조건**</span><span class="sxs-lookup"><span data-stu-id="d5d63-121">**Condition**</span></span>   |<span data-ttu-id="d5d63-122">오프라인으로 전환하는 경우 디바이스의 상태는 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-122">You can monitor the health of devices if they go offline.</span></span> <span data-ttu-id="d5d63-123">[Teams 관리](https://docs.microsoft.com/microsoftteams/devices/device-management) 센터에서 디바이스 관리에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-123">[Learn more](https://docs.microsoft.com/microsoftteams/devices/device-management) about device management in Teams admin center.</span></span> |
|<span data-ttu-id="d5d63-124">**범위**</span><span class="sxs-lookup"><span data-stu-id="d5d63-124">**Scope**</span></span>   |<span data-ttu-id="d5d63-125">규칙 평가 빈도를 언급하여 디바이스 상태 상태를 모니터링할 빈도를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-125">You can specify how frequently you want to monitor device health status by mentioning the rule evaluation frequency.</span></span> <span data-ttu-id="d5d63-126">기본적으로 팀 디바이스는 오프라인 상태인 경우 거의 실시간으로 모니터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-126">By default teams devices will be monitored in near real time if they go offline.</span></span> |
|<span data-ttu-id="d5d63-127">**디바이스 사용자**</span><span class="sxs-lookup"><span data-stu-id="d5d63-127">**Device users**</span></span>   |<span data-ttu-id="d5d63-128">로그인한 사용자를 기반으로 선택하여 사전 오프라인 동상 모니터링이 필요한 디바이스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-128">You can specify which devices need proactive offline statue monitoring by selecting them based on signed-in users.</span></span> <span data-ttu-id="d5d63-129">자세한 내용은 [구성에 대한](#select-devices-for-configuration) 디바이스 선택을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-129">Refer to [Select devices for configuration](#select-devices-for-configuration) for more details.</span></span> |
|<span data-ttu-id="d5d63-130">**작업**  >  **채널 경고**</span><span class="sxs-lookup"><span data-stu-id="d5d63-130">**Actions** > **Channel alert**</span></span>   |<span data-ttu-id="d5d63-131">작업 섹션에서 경고를 받을 팀 채널을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-131">In the Actions section, you can specify teams channels you want to get alerts for.</span></span> <span data-ttu-id="d5d63-132">현재, Admin **Alerts** 및 Notifications라는 기본 팀과 **MonitoringAlerts라는** 채널이 만들어지며 알림이 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-132">Currently, a default team named **Admin Alerts and Notifications** and channel named **MonitoringAlerts** will be created where notifications will be delivered to.</span></span> <BR/> <BR/> <span data-ttu-id="d5d63-133">테넌트의 전역 관리자 및 Teams 관리자가 이 기본 팀에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-133">Global administrators and Teams administrators in your tenant will be automatically added to this default team.</span></span>|
|<span data-ttu-id="d5d63-134">**작업**  >  **웹후크**</span><span class="sxs-lookup"><span data-stu-id="d5d63-134">**Actions** > **Webhook**</span></span>   |<span data-ttu-id="d5d63-135">외부 웹후크(선택 사항)를 사용하여 알림을 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-135">You can also get notifications with an external webhook (optional).</span></span> <span data-ttu-id="d5d63-136">JSON 알림 페이로드가 전송되는 웹후크 섹션에서 외부 공용 웹후크 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-136">Specify an external public webhook URL in the webhook section where a JSON notification payload will be sent.</span></span> <BR/> <BR/>  <span data-ttu-id="d5d63-137">웹후크를 통해 알림 페이로드를 조직의 다른 시스템과 통합하여 사용자 지정 워크플로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-137">The notification payload, via webhooks, can be integrated with other systems in your organization to create custom workflows.</span></span><br/><br/> 

<span data-ttu-id="d5d63-138">**웹후크에 대한 JSON 페이로드 스캐마:**</span><span class="sxs-lookup"><span data-stu-id="d5d63-138">**JSON payload schema for webhook:**</span></span> <BR/><BR/>
<span data-ttu-id="d5d63-139"><pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/></span><span class="sxs-lookup"><span data-stu-id="d5d63-139"><pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/></span></span> 

  <span data-ttu-id="d5d63-140">**샘플 JSON 페이로드:**</span><span class="sxs-lookup"><span data-stu-id="d5d63-140">**Sample JSON payload**:</span></span><br/> <br/> <pre lang="JSON">    { <br/>      <span data-ttu-id="d5d63-141">"AlertTitle":"*sample_device_name* of *User_Name* has become offline",</span><span class="sxs-lookup"><span data-stu-id="d5d63-141">"AlertTitle":"*sample_device_name* of *User_Name* has become offline",</span></span><br/>      <span data-ttu-id="d5d63-142">"DeviceLoggedInUserId": *User_GUID* ,</span><span class="sxs-lookup"><span data-stu-id="d5d63-142">"DeviceLoggedInUserId": *User_GUID* ,</span></span><br/>      <span data-ttu-id="d5d63-143">"DeviceId": *Device_GUID* , </span><span class="sxs-lookup"><span data-stu-id="d5d63-143">"DeviceId": *Device_GUID* , </span></span><br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       <span data-ttu-id="d5d63-144">"TenantId": *Tenant_GUID* , </span><span class="sxs-lookup"><span data-stu-id="d5d63-144">"TenantId": *Tenant_GUID* , </span></span><br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a><span data-ttu-id="d5d63-145">구성에 대한 디바이스 선택</span><span class="sxs-lookup"><span data-stu-id="d5d63-145">Select devices for configuration</span></span>

1. <span data-ttu-id="d5d63-146">해당 디바이스에 로그인한 사용자를 선택하여 모니터링할 Teams 디바이스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-146">You can select Teams devices you want to monitor by selecting users signed in to those devices.</span></span> <span data-ttu-id="d5d63-147">디바이스 **사용자** 섹션에서 **추가를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-147">Select **Add** from the **Device users** section.</span></span>

2. <span data-ttu-id="d5d63-148">디바이스 상태 상태를 모니터링하려는 하나 이상의 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-148">Select one or more users for which you want to monitor device health state</span></span>

   ![디바이스 상태 규칙에서 사용자를 추가합니다.](../media/select-device-users.png )

   <span data-ttu-id="d5d63-150">선택한 사용자 목록이 **디바이스 사용자 섹션에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-150">The selected list of users shows in **Device users** section.</span></span> <span data-ttu-id="d5d63-151">사용자를 추가하거나 제거하여 이 목록을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-151">You can modify this list by adding or removing users.</span></span>

<span data-ttu-id="d5d63-152">선택한 사용자 목록에서 사용하는 모든 로그인 디바이스는 오프라인 상태 상태를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-152">All the sign-in devices used by the selected list of users will be monitored for the offline health state.</span></span>

## <a name="notifications-in-teams-client"></a><span data-ttu-id="d5d63-153">Teams 클라이언트의 알림</span><span class="sxs-lookup"><span data-stu-id="d5d63-153">Notifications in Teams client</span></span>

<span data-ttu-id="d5d63-154">알림은 관리자 경고 및 알림 팀의 자동 생성된 **MonitoringAlerts** 채널에서 **배달됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d5d63-154">The notifications are delivered in the auto-created **MonitoringAlerts** channel of the **Admin Alerts and Notifications** Team.</span></span>

<span data-ttu-id="d5d63-155">디바이스 오프라인 알림에는 다음 정보가 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-155">A device offline notification can include the following information:</span></span>

- <span data-ttu-id="d5d63-156">오프라인인 디바이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-156">The device name that's offline.</span></span>
- <span data-ttu-id="d5d63-157">오프라인 디바이스의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-157">The user of the offline device.</span></span>
- <span data-ttu-id="d5d63-158">디바이스가 오프라인 상태인 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-158">What time the device went offline.</span></span> <span data-ttu-id="d5d63-159">(현재 시간은 UTC로 표시됩니다.)</span><span class="sxs-lookup"><span data-stu-id="d5d63-159">(Currently, the time is presented in UTC.)</span></span>
- <span data-ttu-id="d5d63-160">경고를 제기한 규칙 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-160">The type of rule that raised the alert.</span></span>
- <span data-ttu-id="d5d63-161">경고가 발생하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d63-161">Why an alert is raised.</span></span>
