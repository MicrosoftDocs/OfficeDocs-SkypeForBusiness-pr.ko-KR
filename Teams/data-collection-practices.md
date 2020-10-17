---
title: 데이터 수집 사례
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: 제품 개선을 계획하는데 Teams 및 비즈니스용 Skype 사용과 문제점들을 이해하기 위해 어떻게 Microsoft에서 인구 조사, 사용 및 오류 데이터를 수집하는지 알아봅니다.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651234"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="2f2cc-103">비즈니스용 Skype 및 Microsoft Teams의 데이터 수집 사례</span><span class="sxs-lookup"><span data-stu-id="2f2cc-103">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="2f2cc-104">비즈니스용 Skype 서버 및 비즈니스용 Skype Online, 비즈니스용 skype 및 Microsoft Teams 앱은 해당 제품이 어떻게 사용되는지 이해하고 로그인 오류 등 발생하는 오류의 종류를 Microsoft가 이해하는데 도움이 되도록 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-104">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="2f2cc-105">이 정보는 사용 패턴을 이해하고, 새로운 기능을 계획하며, 문제를 해결하 는데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-105">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="2f2cc-106">몇가지 사용 현황 데이터의 경우 자동으로 수집되지만, 다른 데이터는 관리자 및/또는 사용자가 수집을 허용한 경우에만 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-106">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="2f2cc-107">데이터 수집은 다음 세 가지 범주로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-107">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="2f2cc-108">인구 조사 데이터</span><span class="sxs-lookup"><span data-stu-id="2f2cc-108">Census data</span></span>

- <span data-ttu-id="2f2cc-109">사용 현황 데이터</span><span class="sxs-lookup"><span data-stu-id="2f2cc-109">Usage data</span></span>

- <span data-ttu-id="2f2cc-110">오류 보고 데이터</span><span class="sxs-lookup"><span data-stu-id="2f2cc-110">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="2f2cc-111">인구 조사 데이터</span><span class="sxs-lookup"><span data-stu-id="2f2cc-111">Census data</span></span>

<span data-ttu-id="2f2cc-112">인구 조사 데이터는 비즈니스용 Skype를 제공, 지원 및 개선하기 위해서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-112">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="2f2cc-113">Microsoft Teams 및 비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="2f2cc-113">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="2f2cc-114">여기에는 장치 및 운영 체제 버전과 같은 환경 정보와 지역 및 언어 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-114">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="2f2cc-115">로그인 시도와 실패에대 한 카운터도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-115">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="2f2cc-116">다음은 수집되는 인구 조사 데이터의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-116">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="2f2cc-117">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="2f2cc-117">**Data type**</span></span>|<span data-ttu-id="2f2cc-118">**예**</span><span class="sxs-lookup"><span data-stu-id="2f2cc-118">**Example**</span></span>|<span data-ttu-id="2f2cc-119">**참고**</span><span class="sxs-lookup"><span data-stu-id="2f2cc-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f2cc-120">AppName</span><span class="sxs-lookup"><span data-stu-id="2f2cc-120">AppName</span></span>  <br/> |<span data-ttu-id="2f2cc-121">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="2f2cc-121">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-122">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="2f2cc-122">DeviceModel</span></span>  <br/> |<span data-ttu-id="2f2cc-123">iPhone</span><span class="sxs-lookup"><span data-stu-id="2f2cc-123">iPhone</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-124">OSName</span><span class="sxs-lookup"><span data-stu-id="2f2cc-124">OSName</span></span>  <br/> |<span data-ttu-id="2f2cc-125">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="2f2cc-125">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-126">OSVersion</span><span class="sxs-lookup"><span data-stu-id="2f2cc-126">OSVersion</span></span>  <br/> |<span data-ttu-id="2f2cc-127">8.3</span><span class="sxs-lookup"><span data-stu-id="2f2cc-127">8.3</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-128">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="2f2cc-128">UserLanguage</span></span>  <br/> |<span data-ttu-id="2f2cc-129">EN-US</span><span class="sxs-lookup"><span data-stu-id="2f2cc-129">EN-US</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-130">UserID</span><span class="sxs-lookup"><span data-stu-id="2f2cc-130">UserID</span></span>  <br/> |<span data-ttu-id="2f2cc-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="2f2cc-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="2f2cc-132">ID가 클라이언트에서 한번, 원격 분석 서비스에서 다시 한번 해시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-132">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="2f2cc-133">해시는 ID가 특정 사용자에게 연결될 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-133">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="2f2cc-134">DeviceID</span><span class="sxs-lookup"><span data-stu-id="2f2cc-134">DeviceID</span></span>  <br/> |<span data-ttu-id="2f2cc-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="2f2cc-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="2f2cc-136">장치 ID는 장치에서 임의로 생성되어 원격 분석 서비스로 전송되는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-136">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="2f2cc-137">인구 조사 데이터에는 사용자의 조직이나 사용자를 식별하는 정보가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-137">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="2f2cc-138">자세한 내용은 [비즈니스용 Skype의 개인정보취급방침](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-138">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="2f2cc-139">인구 조사 데이터는 기본적으로 켜져 있으며 관리자 또는 최종 사용자에 의해 해제될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-139">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="2f2cc-140">사용 현황 데이터</span><span class="sxs-lookup"><span data-stu-id="2f2cc-140">Usage data</span></span>

<span data-ttu-id="2f2cc-141">사용 현황 데이터에는 통화 횟수, 보내거나 받은 메시지 수, 참가한 모임 수, 사용한 기능의 빈도 그리고 안정성 문제와 같은 정보를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-141">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="2f2cc-142">사용 현황 데이터는 contoso.com과 같은 조직의 식별 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-142">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="2f2cc-143">다음은 수집되는 사용 현황 데이터의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-143">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="2f2cc-144">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="2f2cc-144">**Data type**</span></span>|<span data-ttu-id="2f2cc-145">**예**</span><span class="sxs-lookup"><span data-stu-id="2f2cc-145">**Example**</span></span>|<span data-ttu-id="2f2cc-146">**참고**</span><span class="sxs-lookup"><span data-stu-id="2f2cc-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f2cc-147">보낸 메시지</span><span class="sxs-lookup"><span data-stu-id="2f2cc-147">IM Sent</span></span>  <br/> |<span data-ttu-id="2f2cc-148">12</span><span class="sxs-lookup"><span data-stu-id="2f2cc-148">12</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-149">받은 메시지</span><span class="sxs-lookup"><span data-stu-id="2f2cc-149">IM Received</span></span>  <br/> |<span data-ttu-id="2f2cc-150">5</span><span class="sxs-lookup"><span data-stu-id="2f2cc-150">5</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-151">모임 참가(시도)</span><span class="sxs-lookup"><span data-stu-id="2f2cc-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="2f2cc-152">5</span><span class="sxs-lookup"><span data-stu-id="2f2cc-152">5</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-153">모임 참가(성공)</span><span class="sxs-lookup"><span data-stu-id="2f2cc-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="2f2cc-154">4</span><span class="sxs-lookup"><span data-stu-id="2f2cc-154">4</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-155">통화/모임 시간</span><span class="sxs-lookup"><span data-stu-id="2f2cc-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="2f2cc-156">30분</span><span class="sxs-lookup"><span data-stu-id="2f2cc-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="2f2cc-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="2f2cc-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2f2cc-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="2f2cc-159">이것은 Office 365에 등록된 조직의 이름이며, 애매하게 만들지 않은 일반 텍스트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="2f2cc-160">사용 현황 데이터에는 사용자를 식별하는 정보가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-160">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="2f2cc-161">사용 현황 데이터 수집은 기본적으로 켜져 있지만 온-프레미스 관리자는 비즈니스용 Skype 서버에서 DisableAutomaticSendTracing 그룹 정책 설정을 이용하여 해당 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="2f2cc-162">이 설정을 끄면 조직의 모든 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="2f2cc-163">자세한 내용은 [클라이언트 부트스트랩 정책 구성](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-163">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="2f2cc-164">최종 사용자는 사용 현황 데이터 수집을 설정하거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-164">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="2f2cc-165">Skype 모임 앱과 조인 시작 관리자 웹 페이지에서 원격 분석을 제어하는 방법은 다음 정책을 통해 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="2f2cc-166">이 정책은 기본값이 False이므로 원격 분석 수집은 기본적으로 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-166">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="2f2cc-167">해당 설정은 풀 단위로 설정되어 있고 Skype 모임 앱을 통해 해당 서버에 호스트 되어 있는 모임에 연결하는 모든 사용자를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-167">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="2f2cc-168">오류 보고 데이터</span><span class="sxs-lookup"><span data-stu-id="2f2cc-168">Error reporting data</span></span>

<span data-ttu-id="2f2cc-169">오류 보고 데이터에는 성능 및 안정성에 대한 정보, 장치 구성, 네트워크 연결 품질, 오류 코드, 오류 로그 및 예외가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-169">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="2f2cc-170">다음은 수집되는 오류 보고 데이터의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-170">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="2f2cc-171">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="2f2cc-171">**Data type**</span></span>|<span data-ttu-id="2f2cc-172">**예**</span><span class="sxs-lookup"><span data-stu-id="2f2cc-172">**Example**</span></span>|<span data-ttu-id="2f2cc-173">**참고**</span><span class="sxs-lookup"><span data-stu-id="2f2cc-173">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f2cc-174">메시지 방향</span><span class="sxs-lookup"><span data-stu-id="2f2cc-174">Message direction</span></span>  <br/> |<span data-ttu-id="2f2cc-175">수신</span><span class="sxs-lookup"><span data-stu-id="2f2cc-175">Incoming</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-176">대화 상태</span><span class="sxs-lookup"><span data-stu-id="2f2cc-176">Conversation state</span></span>  <br/> |<span data-ttu-id="2f2cc-177">유휴</span><span class="sxs-lookup"><span data-stu-id="2f2cc-177">Idle</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-178">대화 스레드 ID</span><span class="sxs-lookup"><span data-stu-id="2f2cc-178">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="2f2cc-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span><span class="sxs-lookup"><span data-stu-id="2f2cc-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="2f2cc-180">UserID</span><span class="sxs-lookup"><span data-stu-id="2f2cc-180">UserID</span></span>  <br/> |<span data-ttu-id="2f2cc-181">amosmarble</span><span class="sxs-lookup"><span data-stu-id="2f2cc-181">amosmarble</span></span> <br/> |<span data-ttu-id="2f2cc-182">ID는 저장하기 전 원격 분석 서비스가 해시하여 암호화 되지 않은 일반 텍스트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-182">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="2f2cc-183">오류 보고 데이터에는 사용자의 IP 주소 및 세션 초기화 프로토콜인 SIP URI(Uniform Resource Identifier)와 같은 개인 식별 정보를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-183">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="2f2cc-184">수집되는 항목에 대한 자세한 내용은 [비즈니스용 Skype 개인정보취급 방침](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-184">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="2f2cc-185">오류 보고에는 두 가지 작업을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-185">Error reporting requires two things:</span></span>

- <span data-ttu-id="2f2cc-186">DisableAutomaticSendTracing 그룹 정책 설정은 서버 또는 테넌트 관리 센터에서 False로 설정됩니다.(기본 상태)</span><span class="sxs-lookup"><span data-stu-id="2f2cc-186">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="2f2cc-187">자세한 내용은 [클라이언트 부트스트랩 정책 구성](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-187">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="2f2cc-188">최종 사용자는 개별적으로 비즈니스용 Skype 클라이언트의 일반 탭에서 옵트인합니다.(기어 아이콘 ![기어를 나타내는 아이콘](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)을 클릭하면 표시된 **일반** 탭으로 **옵션** 대화 상자가 열립니다.) </span><span class="sxs-lookup"><span data-stu-id="2f2cc-188">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![옵션 대화 상자의 데이터 수집 확인란 스크린샷](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="2f2cc-190">Skype 모임 앱의 경우 MeetingUxEnableTelemetry가 오류 보고도 제어합니다. Windows의 크래시가 발생하더라도 Watson 설정이 크래시 정보 업로드를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-190">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="2f2cc-191">데스크톱 클라이언트 대화 상자에 표시 되는 것과 같은 사용자 설정은 Skype 모임 앱에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-191">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="2f2cc-192">자세한 내용은 [비즈니스용 Skype의 일반 옵션 설정](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-192">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="2f2cc-193">[비즈니스용 Skype Online을 위한 네트워크 설정](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)을 참조하여 네트워크를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-193">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="2f2cc-194">중국에서 21vianet이 운영하는 Microsoft 365 또는 Office 365를 사용하는 경우 [21Vianet이 운영하는 비즈니스용 Skype Online 네트워크 설정](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2cc-194">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2f2cc-195">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2f2cc-195">Related topics</span></span>
[<span data-ttu-id="2f2cc-196">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="2f2cc-196">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
