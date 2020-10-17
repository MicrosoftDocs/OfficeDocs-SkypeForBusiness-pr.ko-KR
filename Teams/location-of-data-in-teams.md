---
title: Microsoft Teams의 데이터 위치
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 이 문서에서는 Microsoft Teams에서 데이터가 지리적으로 어디에 위치하는지 알 수 있습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121688"
---
# <a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="fb1ca-103">Microsoft Teams의 데이터 위치</span><span class="sxs-lookup"><span data-stu-id="fb1ca-103">Location of data in Microsoft Teams</span></span>

<span data-ttu-id="fb1ca-104">Teams의 데이터는 Microsoft 365 또는 Office 365 조직과 연결된 지리적 영역에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-104">Data in Teams resides in the geographic region associated with your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="fb1ca-105">현재 Teams는 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 남아프리카 공화국, 대한민국, 스위스(리히텐슈타인 포함), 아랍에미리트, 영국, 미주, APAC 및 EMEA 지역을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-105">Currently, Teams supports the Australia, Canada, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, United Kingdom, Americas, APAC, and EMEA regions.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="fb1ca-106">Teams는 현재 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 대한민국, 남아프리카 공화국, 스위스(리히텐슈타인 포함)의 신규 테넌트에 대한 데이터 보존을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-106">Teams currently offers data residency in Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, United Kingdom, South Korea, South Africa, and Switzerland (which includes Liechtenstein) for new tenants only.</span></span>
> <span data-ttu-id="fb1ca-107">신규 테넌트는 Teams에 로그인한 사용자가 없는 모든 테넌트를 뜻합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-107">A new tenant is defined as any tenant that hasn’t had a single user from the tenant sign in to Teams.</span></span> <span data-ttu-id="fb1ca-108">오스트레일리아, 인도, 일본, 대한민국의 기존 테넌트의 경우 Teams 데이터가 APAC 지역에 계속 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-108">Existing tenants from Australia, India, Japan, and South Korea will continue to have their Teams data stored in the APAC region.</span></span> <span data-ttu-id="fb1ca-109">캐나다의 기존 테넌트는 계속해서 해당 데이터를 미주에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-109">Existing tenants in Canada will continue to have their data stored in the Americas.</span></span> <span data-ttu-id="fb1ca-110">프랑스, 독일, 리히텐슈타인, 아랍에미리트, 영국, 남아프리카 공화국, 스위스의 기존 테넌트의 경우 데이터가 EMEA 지역에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-110">Existing tenants in France, Germany, Liechtenstein, the United Arab Emirates, the United Kingdom, South Africa, and Switzerland will have their data stored in the EMEA region.</span></span>

## <a name="where-your-teams-data-is-stored"></a><span data-ttu-id="fb1ca-111">Teams 데이터가 저장되는 위치</span><span class="sxs-lookup"><span data-stu-id="fb1ca-111">Where your Teams data is stored</span></span>

<span data-ttu-id="fb1ca-112">테넌트의 데이터가 저장되는 지역을 보려면 [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home) > **설정** > **조직 프로필**로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-112">To see which region houses data for your tenant, go to the [Microsoft 365 admin center](https://portal.office.com/adminportal/home) > **Settings** > **Organization profile**.</span></span> <span data-ttu-id="fb1ca-113">**데이터 위치**로 스크롤 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-113">Scroll down to **Data location**.</span></span>

![관리 센터에서 Teams를 포함하는 데이터 위치 테이블의 스크린샷](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a><span data-ttu-id="fb1ca-115">Teams의 미사용 데이터 위치</span><span class="sxs-lookup"><span data-stu-id="fb1ca-115">Location of Teams data at rest</span></span>

<span data-ttu-id="fb1ca-116">Teams 데이터는 콘텐츠 형식에 따라 다르게 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-116">Your Teams data is stored differently depending on the content type.</span></span> 

![Teams 콘텐츠 형식과 미사용 상태로 저장된 위치를 보여주는 다이어그램](media/location-of-data-storage-at-rest.png)

<span data-ttu-id="fb1ca-118">자세한 내용은 Microsoft Teams 아키텍처의 [Ignite 브레이크아웃 세션](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-118">Check out the [Ignite breakout session on Microsoft Teams architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) for an in-depth discussion.</span></span>

### <a name="core-teams-customer-data"></a><span data-ttu-id="fb1ca-119">핵심 Teams의 고객 데이터</span><span class="sxs-lookup"><span data-stu-id="fb1ca-119">Core Teams customer data</span></span>

<span data-ttu-id="fb1ca-120">테넌트가 오스트레일리아, 캐나다, 유럽 연합, 프랑스, 독일, 인도, 일본, 남아프리카 공화국, 대한민국, 스위스(리히텐슈타인 포함), 아랍에미리트, 영국, 미국을 포함하는 경우 Microsoft는 다음과 같은 미사용 고객 데이터를 해당 위치에만 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-120">If your tenant is provisioned in Australia, Canada, the European Union, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, the United Kingdom, or the United States, Microsoft stores the following customer data at rest only within that location:</span></span>

- <span data-ttu-id="fb1ca-121">Teams 채팅, 팀과 채널 대화, 이미지, 음성 메일 메시지 및 연락처</span><span class="sxs-lookup"><span data-stu-id="fb1ca-121">Teams chats, team and channel conversations, images, voicemail messages, and contacts</span></span>
- <span data-ttu-id="fb1ca-122">SharePoint 온라인 사이트 콘텐츠와 해당 사이트에 저장된 파일</span><span class="sxs-lookup"><span data-stu-id="fb1ca-122">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="fb1ca-123">비즈니스용 OneDrive에 업로드된 파일</span><span class="sxs-lookup"><span data-stu-id="fb1ca-123">Files uploaded to OneDrive for Business</span></span>

#### <a name="chat-channel-messages-team-structure"></a><span data-ttu-id="fb1ca-124">채팅, 채널 메시지, 팀 구조</span><span class="sxs-lookup"><span data-stu-id="fb1ca-124">Chat, channel messages, team structure</span></span>

<span data-ttu-id="fb1ca-125">Teams 내 모든 팀은 Microsoft 365 그룹 및 해당 SharePoint 사이트, 그리고 Exchange 사서함에 의해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-125">Every team in Teams is backed by a Microsoft 365 Group and its SharePoint site and Exchange mailbox.</span></span> <span data-ttu-id="fb1ca-126">비공개 채팅(그룹 채팅 포함), 채널 내 대화의 일부로 전송된 메시지, 그리고 팀과 채널 구조 또한 Azure에서 실행되는 채팅 서비스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-126">Private chats (including group chats), messages sent as part of a conversation in a channel, and the structure of teams and channels are stored in a chat service running in Azure.</span></span> <span data-ttu-id="fb1ca-127">데이터는 정보 보호 기능을 위해 사용자 및 그룹 사서함의 숨겨진 폴더에도 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-127">The data is also stored in a hidden folder in the user and group mailboxes to enable Information Protection features.</span></span>

#### <a name="voicemail-and-contacts"></a><span data-ttu-id="fb1ca-128">음성 메일 및 연락처</span><span class="sxs-lookup"><span data-stu-id="fb1ca-128">Voicemail and contacts</span></span>

<span data-ttu-id="fb1ca-129">음성 메일은 Exchange에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-129">Voicemails are stored in Exchange.</span></span> <span data-ttu-id="fb1ca-130">연락처는 Exchange 기반 클라우드 데이터 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-130">Contacts are stored in Exchange-based cloud data store.</span></span> <span data-ttu-id="fb1ca-131">Exchange와 Exchange 기반 클라우드 스토어는 이미 전세계 데이터 센터 위치에 각각 데이터 보존을 제공하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-131">Exchange and the Exchange-based cloud store already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="fb1ca-132">모든 팀의 경우 음성 메일과 연락처가 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 남아프리카 공화국, 대한민국, 스위스 (리히텐슈타인 포함) 및 미국에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-132">For all teams, voicemail and contacts are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, Switzerland (includes Liechtenstein), and the United States.</span></span> <span data-ttu-id="fb1ca-133">기타 국가들의 경우 테넌트 선호도에 따라 파일이 미국, 유럽 또는 아시아 태평양 지역에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-133">For all other countries, files are stored in the US, Europe, or Asia-Pacific location based on tenant affinity.</span></span>

#### <a name="images-and-media"></a><span data-ttu-id="fb1ca-134">이미지와 미디어</span><span class="sxs-lookup"><span data-stu-id="fb1ca-134">Images and media</span></span>

<span data-ttu-id="fb1ca-135">채팅에 사용 되는 미디어(저장 되지 않은 Giphy GIF를 제외하고, 원본 Giphy 서비스 URL의 참조 링크. Giphy는 Microsoft 서비스가 아님.)는 채팅 서비스와 동일한 위치에 배포되는 Azure 기반 미디어 서비스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-135">Media used in chats (except for Giphy GIFs which aren't stored but are a reference link to the original Giphy service URL, Giphy is a non-Microsoft service) is stored in an Azure-based media service that is deployed to the same locations as the chat service.</span></span>

#### <a name="files"></a><span data-ttu-id="fb1ca-136">파일</span><span class="sxs-lookup"><span data-stu-id="fb1ca-136">Files</span></span>

<span data-ttu-id="fb1ca-137">채널에서 다른 사람이 공유하는 파일(OneNote와 Wiki 포함)은 팀의 SharePoint 사이트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-137">Files (including OneNote and Wiki) that somebody shares in a channel are stored in the team’s SharePoint site.</span></span> <span data-ttu-id="fb1ca-138">비공개 채팅 또는 모임 또는 통화 중 채팅에서 공유된 파일은 파일을 공유 한 사용자의 비즈니스용 OneDrive에 업로드되고 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-138">Files shared in a private chat or a chat during a meeting or call are uploaded and stored in the OneDrive for the Business account of the user who shares the file.</span></span> <span data-ttu-id="fb1ca-139">Exchange, SharePoint 및 OneDrive는 이미 전세계 데이터 센터 위치에 각각 데이터 보존을 제공하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-139">Exchange, SharePoint and OneDrive already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="fb1ca-140">따라서 기존 고객의 경우 Teams 경험의 일부인 모든 파일, OneNote 노트북, Teams 위키 콘텐츠와 사서함이 이미 테넌트 선호도에 따른 위치에 저장되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-140">So, for existing customers, all files, OneNote notebooks, Teams wiki content, and mailboxes that are part of the Teams experience are already stored in the location based on your tenant affinity.</span></span> <span data-ttu-id="fb1ca-141">파일은 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 남아프리카 공화국, 대한민국, 스위스(리히텐슈타인 포함) 국내에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-141">Files are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, and Switzerland (which includes Liechtenstein).</span></span> <span data-ttu-id="fb1ca-142">기타 국가들의 경우 테넌트 선호도에 따라 파일이 미국, 유럽 또는 아시아태평양 지역에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-142">For all other countries, files are stored in the US, Europe, or Asia Pacific location based on tenant affinity.</span></span>

### <a name="datacenter-locations"></a><span data-ttu-id="fb1ca-143">데이터 센터 위치</span><span class="sxs-lookup"><span data-stu-id="fb1ca-143">Datacenter locations</span></span>

<span data-ttu-id="fb1ca-144">이 섹션에 설명된 Teams 서비스는 아래와 같은 위치에 미사용 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-144">The Teams services described in this section store data at rest in the following locations:</span></span>

|<span data-ttu-id="fb1ca-145">국가 또는 지역</span><span class="sxs-lookup"><span data-stu-id="fb1ca-145">Country or region</span></span>  |<span data-ttu-id="fb1ca-146">데이터센터 위치</span><span class="sxs-lookup"><span data-stu-id="fb1ca-146">Datacenter location</span></span> |
|---------|---------|
|<span data-ttu-id="fb1ca-147">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="fb1ca-147">Australia</span></span>   |<span data-ttu-id="fb1ca-148">뉴사우스웨일스 및 빅토리아</span><span class="sxs-lookup"><span data-stu-id="fb1ca-148">New South Wales and Victoria</span></span>         |
|<span data-ttu-id="fb1ca-149">캐나다</span><span class="sxs-lookup"><span data-stu-id="fb1ca-149">Canada</span></span>    |<span data-ttu-id="fb1ca-150">퀘벡 시티 및 토론토</span><span class="sxs-lookup"><span data-stu-id="fb1ca-150">Quebec City and Toronto</span></span>         |
|<span data-ttu-id="fb1ca-151">프랑스</span><span class="sxs-lookup"><span data-stu-id="fb1ca-151">France</span></span>    |<span data-ttu-id="fb1ca-152">마르세유 및 파리</span><span class="sxs-lookup"><span data-stu-id="fb1ca-152">Marseille and Paris</span></span>         |
|<span data-ttu-id="fb1ca-153">독일</span><span class="sxs-lookup"><span data-stu-id="fb1ca-153">Germany</span></span>    |<span data-ttu-id="fb1ca-154">베를린 및 프랑크푸르트</span><span class="sxs-lookup"><span data-stu-id="fb1ca-154">Berlin and Frankfurt</span></span>      |
|<span data-ttu-id="fb1ca-155">인도</span><span class="sxs-lookup"><span data-stu-id="fb1ca-155">India</span></span>   |<span data-ttu-id="fb1ca-156">첸나이 및 푼</span><span class="sxs-lookup"><span data-stu-id="fb1ca-156">Chennai and Pune</span></span>        |
|<span data-ttu-id="fb1ca-157">일본</span><span class="sxs-lookup"><span data-stu-id="fb1ca-157">Japan</span></span>    |<span data-ttu-id="fb1ca-158">도쿄(사이타마) 및 오사카</span><span class="sxs-lookup"><span data-stu-id="fb1ca-158">Tokyo (Saitama) and Osaka</span></span>         |
|<span data-ttu-id="fb1ca-159">리히텐슈타인</span><span class="sxs-lookup"><span data-stu-id="fb1ca-159">Liechtenstein</span></span>   |<span data-ttu-id="fb1ca-160">제네바 및 취리히</span><span class="sxs-lookup"><span data-stu-id="fb1ca-160">Geneva and Zurich</span></span>       |
|<span data-ttu-id="fb1ca-161">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="fb1ca-161">South Africa</span></span>     |<span data-ttu-id="fb1ca-162">요하네스버그 및 케이프타운</span><span class="sxs-lookup"><span data-stu-id="fb1ca-162">Johannesburg and Cape Town</span></span>         |
|<span data-ttu-id="fb1ca-163">대한민국</span><span class="sxs-lookup"><span data-stu-id="fb1ca-163">South Korea</span></span>     |<span data-ttu-id="fb1ca-164">서울 및 부산</span><span class="sxs-lookup"><span data-stu-id="fb1ca-164">Seoul and Busan</span></span>         |
|<span data-ttu-id="fb1ca-165">스위스</span><span class="sxs-lookup"><span data-stu-id="fb1ca-165">Switzerland</span></span>    |<span data-ttu-id="fb1ca-166">제네바 및 취리히</span><span class="sxs-lookup"><span data-stu-id="fb1ca-166">Geneva and Zurich</span></span>       |
|<span data-ttu-id="fb1ca-167">아랍에미리트</span><span class="sxs-lookup"><span data-stu-id="fb1ca-167">United Arab Emirates</span></span>     |<span data-ttu-id="fb1ca-168">아부다비 및 두바이</span><span class="sxs-lookup"><span data-stu-id="fb1ca-168">Abu Dhabi and Dubai</span></span>         |
|<span data-ttu-id="fb1ca-169">영국</span><span class="sxs-lookup"><span data-stu-id="fb1ca-169">United Kingdom</span></span>     | <span data-ttu-id="fb1ca-170">카디프 및 런던</span><span class="sxs-lookup"><span data-stu-id="fb1ca-170">Cardiff and London</span></span>        |
|<span data-ttu-id="fb1ca-171">미주-북부 및 남부(AMER)</span><span class="sxs-lookup"><span data-stu-id="fb1ca-171">Americas – North, and South (AMER)</span></span> |<span data-ttu-id="fb1ca-172">캘리포니아 베이 및 버지니아 보이드턴</span><span class="sxs-lookup"><span data-stu-id="fb1ca-172">Bay, CA and Boydton, VA</span></span>       |
|<span data-ttu-id="fb1ca-173">아시아 태평양(APAC)</span><span class="sxs-lookup"><span data-stu-id="fb1ca-173">Asia Pacific (APAC)</span></span>  |<span data-ttu-id="fb1ca-174">싱가포르 및 홍콩 특별행정구</span><span class="sxs-lookup"><span data-stu-id="fb1ca-174">Singapore and Hong Kong</span></span>        |
|<span data-ttu-id="fb1ca-175">유럽, 중동 및 아시아(EMEA)</span><span class="sxs-lookup"><span data-stu-id="fb1ca-175">Europe, Middle East, and Asia (EMEA)</span></span>   |<span data-ttu-id="fb1ca-176">더블린 및 암스테르담</span><span class="sxs-lookup"><span data-stu-id="fb1ca-176">Dublin and Amsterdam</span></span>        |

> [!NOTE]
> <span data-ttu-id="fb1ca-177">리히텐슈타인의 경우 데이터가 미사용 상태로 제네바 및 취리히에 위치한 스위스 데이터 센터에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-177">For Liechtenstein, data is stored at rest in the Switzerland data centers in Geneva and Zurich.</span></span>

### <a name="data-stored-with-a-third-party-storage-provider"></a><span data-ttu-id="fb1ca-178">제3자 저장소 공급자에 저장되는 데이터</span><span class="sxs-lookup"><span data-stu-id="fb1ca-178">Data stored with a third-party storage provider</span></span>

<span data-ttu-id="fb1ca-179">사용자가 제3자 저장소 공급자를 이용하여 파일을 저장할 수 있도록 허용 하는 조직의 경우, 해당 서비스의 저장소 위치에 종속되므로 해당 서비스에 대한 미사용 데이터의 위치를 별도로 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-179">Organizations who allow users to store files with a third-party storage provider are dependent on the storage location of those services and should, therefore, review the location of data at rest for those services separately.</span></span>

- <span data-ttu-id="fb1ca-180">**탭**: 탭은 사용자가 앱 및 서비스의 정보를 채널에 고정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-180">**Tabs**: Tabs allow users to pin information from apps and services to a channel.</span></span> <span data-ttu-id="fb1ca-181">따라서 데이터가 저장되는 탭 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-181">Thus, it varies by type of the tab where the data is stored.</span></span> <span data-ttu-id="fb1ca-182">탭 자체는 데이터를 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-182">The tab itself doesn't store any data.</span></span> <span data-ttu-id="fb1ca-183">예를 들어 SharePoint 탭의 경우 SharePoint 사이트 모음을 포함하는 위치에 따라 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-183">For example, a SharePoint tab will store data based on where the SharePoint site collection was provisioned.</span></span> <span data-ttu-id="fb1ca-184">파트너의 정보를 포함하는 탭은 파트너가 사용하는 시스템에 데이터를 바로 저장하고 보기만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-184">A tab that includes information from a partner will store the data directly in the system used by the partner and only present a view of it.</span></span>
- <span data-ttu-id="fb1ca-185">**기타 파트너 앱**: Microsoft는 Teams 환경 내에서 사용할 수 있는 파트너 제공 앱 및 서비스에 대한 데이터 보존을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-185">**Other partner apps**: Microsoft doesn't provide any data residency support for apps and services from partners that you might be using within the Teams experience.</span></span> <span data-ttu-id="fb1ca-186">해당 솔루션의 정보를 직접 검토하여 데이터가 저장되는 위치를 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="fb1ca-186">Review information from those solutions directly to learn about where their data is being stored.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb1ca-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb1ca-187">See also</span></span>

- [<span data-ttu-id="fb1ca-188">Microsoft Teams에서 아랍에미리트의 데이터 보존을 시작합니다</span><span class="sxs-lookup"><span data-stu-id="fb1ca-188">Microsoft Teams launches United Arab Emirates Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [<span data-ttu-id="fb1ca-189">Microsoft Teams에서 대한민국의 데이터 보존을 시작합니다</span><span class="sxs-lookup"><span data-stu-id="fb1ca-189">Microsoft Teams launches South Korean Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [<span data-ttu-id="fb1ca-190">Microsoft Teams에서 남아프리카 공화국의 데이터 보존을 시작합니다</span><span class="sxs-lookup"><span data-stu-id="fb1ca-190">Microsoft Teams launches South African Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [<span data-ttu-id="fb1ca-191">Microsoft Teams에서 프랑스의 데이터 보존을 시작합니다</span><span class="sxs-lookup"><span data-stu-id="fb1ca-191">Microsoft Teams Launches France Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [<span data-ttu-id="fb1ca-192">Microsoft Teams에서 인도의 데이터 보존을 시작하고 기타 지역에서도 곧 시작할 예정입니다</span><span class="sxs-lookup"><span data-stu-id="fb1ca-192">Microsoft Teams launches India Data Residency, other geos coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [<span data-ttu-id="fb1ca-193">Microsoft Teams에서 오스트레일리아 및 일본의 데이터 보존을 시작합니다</span><span class="sxs-lookup"><span data-stu-id="fb1ca-193">Microsoft Teams Launches Australia and Japan Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [<span data-ttu-id="fb1ca-194">Microsoft Teams에서 캐나다 데이터 보존을 시작하고 곧 오스트레일리아 및 일본에서도 시작할 예정입니다</span><span class="sxs-lookup"><span data-stu-id="fb1ca-194">Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
