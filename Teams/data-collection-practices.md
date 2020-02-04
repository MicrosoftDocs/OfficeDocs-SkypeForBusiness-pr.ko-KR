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
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: Microsoft는 비즈니스용 Skype를 사용 하는 방법과 사용자에 게 문제가 발생 하는 방식을 이해 하기 위해 인구 조사, 사용, 오류 데이터를 수집 합니다. 데이터는 제품 개선을 계획 하는 데 사용 됩니다.
ms.openlocfilehash: e84946fd8c61daad7e16f8f7e248f4a0e06c2ae4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680465"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="d3ba1-104">비즈니스용 Skype 및 Microsoft 팀 데이터 수집 방법</span><span class="sxs-lookup"><span data-stu-id="d3ba1-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="d3ba1-105">비즈니스용 skype 서버 및 비즈니스용 skype Online 및 Microsoft 팀 용 skype 앱, Microsoft에서 이러한 제품을 사용 하는 방법과 로그인 오류 등의 오류 종류에 대 한 데이터를 수집 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-105">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="d3ba1-106">이 정보는 사용 패턴을 이해 하 고, 새 기능을 계획 하며, 문제 영역을 해결 하 고 해결 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="d3ba1-107">일부 사용 데이터는 자동으로 수집 되지만, 관리자 및/또는 사용자가 허용 하도록 선택한 경우에만 다른 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-107">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="d3ba1-108">데이터 수집은 다음 세 가지 범주로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-108">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="d3ba1-109">인구 조사 데이터</span><span class="sxs-lookup"><span data-stu-id="d3ba1-109">Census data</span></span>

- <span data-ttu-id="d3ba1-110">사용 현황 데이터</span><span class="sxs-lookup"><span data-stu-id="d3ba1-110">Usage data</span></span>

- <span data-ttu-id="d3ba1-111">오류 보고 데이터</span><span class="sxs-lookup"><span data-stu-id="d3ba1-111">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="d3ba1-112">인구 조사 데이터</span><span class="sxs-lookup"><span data-stu-id="d3ba1-112">Census data</span></span>

<span data-ttu-id="d3ba1-113">인구 조사 데이터는 비즈니스용 Skype를 제공, 지원 및 개선 하는 용도로만 확보 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="d3ba1-114">Microsoft 팀 및 비즈니스용 Skype Online.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-114">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="d3ba1-115">여기에는 장치, 운영 체제 버전, 국가 및 언어 설정 등의 환경 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="d3ba1-116">또한 로그인 시도 및 실패에 대 한 카운터도 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="d3ba1-117">다음은 수집 되는 인구 조사 데이터의 몇 가지 구체적인 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="d3ba1-118">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="d3ba1-118">**Data type**</span></span>|<span data-ttu-id="d3ba1-119">**예**</span><span class="sxs-lookup"><span data-stu-id="d3ba1-119">**Example**</span></span>|<span data-ttu-id="d3ba1-120">**상속자**</span><span class="sxs-lookup"><span data-stu-id="d3ba1-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3ba1-121">AppName</span><span class="sxs-lookup"><span data-stu-id="d3ba1-121">AppName</span></span>  <br/> |<span data-ttu-id="d3ba1-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="d3ba1-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="d3ba1-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="d3ba1-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="d3ba1-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-125">OSName</span><span class="sxs-lookup"><span data-stu-id="d3ba1-125">OSName</span></span>  <br/> |<span data-ttu-id="d3ba1-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="d3ba1-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-127">OSVersion</span><span class="sxs-lookup"><span data-stu-id="d3ba1-127">OSVersion</span></span>  <br/> |<span data-ttu-id="d3ba1-128">8.3</span><span class="sxs-lookup"><span data-stu-id="d3ba1-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-129">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="d3ba1-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="d3ba1-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="d3ba1-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-131">UserID</span><span class="sxs-lookup"><span data-stu-id="d3ba1-131">UserID</span></span>  <br/> |<span data-ttu-id="d3ba1-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="d3ba1-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="d3ba1-133">ID는 클라이언트에서 한 번, 원격 분석 서비스에서 두 번 해시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-133">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="d3ba1-134">해시를 사용 하면 ID를 특정 사용자에 게 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-134">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="d3ba1-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="d3ba1-135">DeviceID</span></span>  <br/> |<span data-ttu-id="d3ba1-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="d3ba1-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="d3ba1-137">장치 ID는 장치에서 임의로 생성 되 고 원격 분석 서비스로 전송 되는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="d3ba1-138">인구 조사 데이터에는 조직이 나 사용자를 식별 하는 정보가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-138">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="d3ba1-139">자세한 내용은 [비즈니스용 Skype 개인 정보 취급 방침](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-139">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="d3ba1-140">인구 조사 data는 기본적으로 설정 되어 있으며 관리자 또는 최종 사용자가 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="d3ba1-141">사용 현황 데이터</span><span class="sxs-lookup"><span data-stu-id="d3ba1-141">Usage data</span></span>

<span data-ttu-id="d3ba1-142">사용 현황 데이터에는 통화 수, 보내거나 받은 메신저 대화, 참가 한 모임 수, 사용 하는 기능 빈도, 안정성 문제 등의 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="d3ba1-143">사용 현황 데이터에는 contoso.com 같은 조직을 식별 하는 정보가 포함 될 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-143">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="d3ba1-144">다음은 수집 되는 사용 현황 데이터의 몇 가지 구체적인 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-144">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="d3ba1-145">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="d3ba1-145">**Data type**</span></span>|<span data-ttu-id="d3ba1-146">**예**</span><span class="sxs-lookup"><span data-stu-id="d3ba1-146">**Example**</span></span>|<span data-ttu-id="d3ba1-147">**상속자**</span><span class="sxs-lookup"><span data-stu-id="d3ba1-147">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3ba1-148">보낸 메신저 대화</span><span class="sxs-lookup"><span data-stu-id="d3ba1-148">IM Sent</span></span>  <br/> |<span data-ttu-id="d3ba1-149">까지</span><span class="sxs-lookup"><span data-stu-id="d3ba1-149">12</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-150">수신 된 메신저 대화</span><span class="sxs-lookup"><span data-stu-id="d3ba1-150">IM Received</span></span>  <br/> |<span data-ttu-id="d3ba1-151">5mb</span><span class="sxs-lookup"><span data-stu-id="d3ba1-151">5</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-152">모임 참가 (시도)</span><span class="sxs-lookup"><span data-stu-id="d3ba1-152">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="d3ba1-153">5mb</span><span class="sxs-lookup"><span data-stu-id="d3ba1-153">5</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-154">모임 참가 (성공)</span><span class="sxs-lookup"><span data-stu-id="d3ba1-154">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="d3ba1-155">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="d3ba1-155">4</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-156">통화/회의 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="d3ba1-156">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="d3ba1-157">30 분</span><span class="sxs-lookup"><span data-stu-id="d3ba1-157">30 mins</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-158">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="d3ba1-158">FederationPartner</span></span>  <br/> |<span data-ttu-id="d3ba1-159">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d3ba1-159">Microsoft.com</span></span>  <br/> |<span data-ttu-id="d3ba1-160">이것은 Office 365에 등록 된 조직의 이름이 며 일반 텍스트로 전송 되므로 난독 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-160">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="d3ba1-161">사용 현황 데이터에는 사용자를 식별 하는 정보가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-161">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="d3ba1-162">사용 현황 데이터 수집은 기본적으로 설정 되어 있지만 온-프레미스 관리자는 비즈니스용 Skype 서버의 Disable자동 Sendtracing 그룹 정책 설정을 사용 하 여 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-162">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="d3ba1-163">이 설정을 끄면 조직의 모든 사용자에 게 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-163">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="d3ba1-164">자세한 내용은 [클라이언트 부트스트랩 정책 구성을](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-164">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="d3ba1-165">최종 사용자는 사용 현황 데이터 수집을 설정 하거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-165">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="d3ba1-166">Skype 모임 앱 및 참가 시작 관리자 웹 페이지의 경우이 정책을 통해 원격 분석을 제어 하는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-166">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="d3ba1-167">이 정책의 기본값은 false 이므로 원격 분석 수집은 기본적으로 해제 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-167">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="d3ba1-168">이 설정은 풀 단위이 고 Skype 모임 앱에 연결 하는 모든 사용자를 해당 서버에서 호스트 하는 모임에 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-168">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="d3ba1-169">오류 보고 데이터</span><span class="sxs-lookup"><span data-stu-id="d3ba1-169">Error reporting data</span></span>

<span data-ttu-id="d3ba1-170">오류 보고 데이터에는 성능 및 안정성, 장치 구성, 네트워크 연결 품질, 오류 코드, 오류 로그 및 예외에 대 한 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-170">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="d3ba1-171">다음은 수집 되는 오류 보고 데이터의 몇 가지 구체적인 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-171">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="d3ba1-172">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="d3ba1-172">**Data type**</span></span>|<span data-ttu-id="d3ba1-173">**예**</span><span class="sxs-lookup"><span data-stu-id="d3ba1-173">**Example**</span></span>|<span data-ttu-id="d3ba1-174">**상속자**</span><span class="sxs-lookup"><span data-stu-id="d3ba1-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3ba1-175">메시지 방향</span><span class="sxs-lookup"><span data-stu-id="d3ba1-175">Message direction</span></span>  <br/> |<span data-ttu-id="d3ba1-176">들어옴</span><span class="sxs-lookup"><span data-stu-id="d3ba1-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-177">대화 상태</span><span class="sxs-lookup"><span data-stu-id="d3ba1-177">Conversation state</span></span>  <br/> |<span data-ttu-id="d3ba1-178">이면</span><span class="sxs-lookup"><span data-stu-id="d3ba1-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-179">대화 스레드 ID</span><span class="sxs-lookup"><span data-stu-id="d3ba1-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="d3ba1-180">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="d3ba1-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="d3ba1-181">UserID</span><span class="sxs-lookup"><span data-stu-id="d3ba1-181">UserID</span></span>  <br/> |<span data-ttu-id="d3ba1-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="d3ba1-182">amosmarble</span></span> <br/> |<span data-ttu-id="d3ba1-183">ID는 저장 하기 전에 원격 분석 서비스가 해시 하는 일반 텍스트로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="d3ba1-184">오류 보고 데이터에는 사용자의 IP 주소 및 세션 초기화 프로토콜 Uniform Resource Identifier (SIP URI)와 같은 개인 식별 가능한 정보도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-184">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="d3ba1-185">수집 된 내용에 대 한 자세한 설명은 비즈니스용 [Skype 개인 정보 취급 방침](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-185">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="d3ba1-186">오류 보고에는 두 가지 사항이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-186">Error reporting requires two things:</span></span>

- <span data-ttu-id="d3ba1-187">Disable자동 Sendtracing 그룹 정책 설정이 서버나 테 넌 트 관리 센터 (기본 상태인 경우)에서 False로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-187">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="d3ba1-188">자세한 내용은 [클라이언트 부트스트랩 정책 구성을](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-188">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="d3ba1-189">최종 사용자 ![의 일반 탭 (기어 아이콘을 클릭 하면 기어를 ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) 나타내는 아이콘에는 비즈니스용 Skype 클라이언트에서 **일반** 탭이 표시 됨)의 **옵션** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-189">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![옵션 대화 상자의 데이터 수집 확인란 스크린샷](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="d3ba1-191">Skype 모임 앱의 경우 MeetingUxEnableTelemetry는 또한 오류 보고 기능을 제어 하며, Windows에서의 충돌은 물론, Watson 설정이 크래시 정보를 업로드 하는 것을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-191">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="d3ba1-192">데스크톱 클라이언트 대화 상자에 표시 되는 것과 같은 Skype 모임 앱에 대 한 사용자 설정은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-192">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="d3ba1-193">자세한 내용은 비즈니스용 [Skype에서 일반 옵션 설정을](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-193">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="d3ba1-194">네트워크 설정을 위해 [비즈니스용 Skype Online에 대 한 네트워크 설정을](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-194">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="d3ba1-195">중국에서 21Vianet에서 운영 하는 Office 365를 사용 하는 경우 [21vianet에서 운영 하는 비즈니스용 Skype Online을 위한 네트워크 설정을](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ba1-195">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3ba1-196">관련 주제</span><span class="sxs-lookup"><span data-stu-id="d3ba1-196">Related topics</span></span>
[<span data-ttu-id="d3ba1-197">사용자 환경 개선 프로그램</span><span class="sxs-lookup"><span data-stu-id="d3ba1-197">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/default.mspx)

[<span data-ttu-id="d3ba1-198">오디오 회의 및 통화 요금제 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="d3ba1-198">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
