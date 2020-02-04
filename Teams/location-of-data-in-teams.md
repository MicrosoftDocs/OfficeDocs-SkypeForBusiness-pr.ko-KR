---
title: Microsoft 팀의 데이터 위치
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: Microsoft 팀에서 데이터가 저장 되는 위치에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24432b0854ac0c4256f5d097bacfca5f1a392d72
ms.sourcegitcommit: 2cb46af39a0d116e8fd020aa04bd2ecbd6998a5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41679044"
---
# <a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="ba537-103">Microsoft 팀의 데이터 위치</span><span class="sxs-lookup"><span data-stu-id="ba537-103">Location of data in Microsoft Teams</span></span>

<span data-ttu-id="ba537-104">팀의 데이터는 Office 365 테 넌 트와 연결 된 지리적 영역에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-104">Data in Teams resides in the geographic region associated with your Office 365 tenant.</span></span> <span data-ttu-id="ba537-105">현재, 팀은 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 남아프리카, 대한민국, 스위스 (리히텐슈타인 포함), 미국, 호주, 영국, 미국, APAC, EMEA 지역 등을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-105">Currently, Teams supports the Australia, Canada, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, United Kingdom, Americas, APAC, and EMEA regions.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ba537-106">현재 팀은 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 미국 아랍, 영국, 대한민국, 남아프리카, 스위스 (리히텐슈타인 포함) 새 테 넌 트에만 데이터 영주권을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-106">Teams currently offers data residency in Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, United Kingdom, South Korea, South Africa, and Switzerland (which includes Liechtenstein) for new tenants only.</span></span>
> <span data-ttu-id="ba537-107">새 테 넌 트가 테 넌 트에서 팀에 로그인 한 사용자가 없는 모든 테 넌 트로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-107">A new tenant is defined as any tenant that hasn’t had a single user from the tenant sign in to Teams.</span></span> <span data-ttu-id="ba537-108">오스트레일리아, 인도, 일본, 대한민국의 기존 테 넌 트는 계속 해 서 자신의 팀 데이터를 APAC 지역에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-108">Existing tenants from Australia, India, Japan, and South Korea will continue to have their Teams data stored in the APAC region.</span></span> <span data-ttu-id="ba537-109">캐나다의 기존 테 넌 트는 계속 해 서 해당 데이터를 미주에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-109">Existing tenants in Canada will continue to have their data stored in the Americas.</span></span> <span data-ttu-id="ba537-110">프랑스, 독일, 리히텐슈타인, 미국 아랍, 영국, 남아프리카, 스위스의 기존 테 넌 트는 EMEA 지역에 저장 된 데이터를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-110">Existing tenants in France, Germany, Liechtenstein, the United Arab Emirates, the United Kingdom, South Africa, and Switzerland will have their data stored in the EMEA region.</span></span>

## <a name="where-your-teams-data-is-stored"></a><span data-ttu-id="ba537-111">팀 데이터가 저장 되는 위치</span><span class="sxs-lookup"><span data-stu-id="ba537-111">Where your Teams data is stored</span></span>

<span data-ttu-id="ba537-112">테 넌 트에 대 한 데이터가 들어 있는 영역을 확인 하려면 [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home) > **설정** > **조직 프로필로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-112">To see which region houses data for your tenant, go to the [Microsoft 365 admin center](https://portal.office.com/adminportal/home) > **Settings** > **Organization profile**.</span></span> <span data-ttu-id="ba537-113">아래로 스크롤하여 **데이터 위치로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-113">Scroll down to **Data location**.</span></span>

![관리 센터의 팀을 비롯 한 데이터 위치 표 스크린샷](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a><span data-ttu-id="ba537-115">팀 데이터의 남은 위치</span><span class="sxs-lookup"><span data-stu-id="ba537-115">Location of Teams data at rest</span></span>

<span data-ttu-id="ba537-116">팀 데이터는 콘텐츠 형식에 따라 다르게 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-116">Your Teams data is stored differently depending on the content type.</span></span> 

![팀 콘텐츠 형식 및 나머지 위치에서 저장 되는 위치를 보여 주는 다이어그램](media/location-of-data-storage-at-rest.png)

<span data-ttu-id="ba537-118">자세한 내용은 [Microsoft 팀 아키텍처의 Ignite 브레이크 아웃 세션](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ba537-118">Check out the [Ignite breakout session on Microsoft Teams architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) for an in-depth discussion.</span></span>

### <a name="core-teams-customer-data"></a><span data-ttu-id="ba537-119">핵심 팀 고객 데이터</span><span class="sxs-lookup"><span data-stu-id="ba537-119">Core Teams customer data</span></span>

<span data-ttu-id="ba537-120">테 넌 트가 오스트레일리아, 캐나다, 유럽 연합, 프랑스, 독일, 인도, 일본, 남아프리카, 대한민국, 스위스 (리히텐슈타인 포함), 미국, 영국 또는 미국, Microsoft 상점 해당 위치 내 에서만 남은 고객 데이터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-120">If your tenant is provisioned in Australia, Canada, the European Union, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, the United Kingdom, or the United States, Microsoft stores the following customer data at rest only within that location:</span></span>

- <span data-ttu-id="ba537-121">팀 채팅, 팀 및 채널 대화, 이미지, 보이스 메일 메시지, 연락처</span><span class="sxs-lookup"><span data-stu-id="ba537-121">Teams chats, team and channel conversations, images, voicemail messages, and contacts</span></span>
- <span data-ttu-id="ba537-122">SharePoint Online 사이트 콘텐츠 및 해당 사이트에 저장 된 파일</span><span class="sxs-lookup"><span data-stu-id="ba537-122">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="ba537-123">비즈니스용 OneDrive에 업로드 된 파일</span><span class="sxs-lookup"><span data-stu-id="ba537-123">Files uploaded to OneDrive for Business</span></span>

#### <a name="chat-channel-messages-team-structure"></a><span data-ttu-id="ba537-124">채팅, 채널 메시지, 팀 구조</span><span class="sxs-lookup"><span data-stu-id="ba537-124">Chat, channel messages, team structure</span></span>

<span data-ttu-id="ba537-125">팀의 모든 팀은 Office 365 그룹과 해당 SharePoint 사이트 및 Exchange 사서함에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-125">Every team in Teams is backed by an Office 365 Group and its SharePoint site and Exchange mailbox.</span></span> <span data-ttu-id="ba537-126">개인 채팅 (그룹 채팅 포함), 채널에서 대화의 일부로 전송 된 메시지, 팀 및 채널의 구조는 Azure에서 실행 되는 채팅 서비스에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-126">Private chats (including group chats), messages sent as part of a conversation in a channel, and the structure of teams and channels are stored in a chat service running in Azure.</span></span> <span data-ttu-id="ba537-127">정보 보호 기능을 사용 하도록 설정 하기 위해 사용자 및 그룹 사서함의 숨겨진 폴더에도 데이터가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-127">The data is also stored in a hidden folder in the user and group mailboxes to enable Information Protection features.</span></span>

#### <a name="voicemail-and-contacts"></a><span data-ttu-id="ba537-128">보이스 메일 및 연락처</span><span class="sxs-lookup"><span data-stu-id="ba537-128">Voicemail and contacts</span></span>

<span data-ttu-id="ba537-129">보이스 메일 Exchange에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-129">Voicemails are stored in Exchange.</span></span> <span data-ttu-id="ba537-130">연락처는 Exchange 기반 클라우드 데이터 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-130">Contacts are stored in Exchange-based cloud data store.</span></span> <span data-ttu-id="ba537-131">Exchange 및 Exchange 기반 클라우드 저장소는 전세계의 모든 데이터 센터 geos에서 데이터 영주권를 이미 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-131">Exchange and the Exchange-based cloud store already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="ba537-132">모든 팀에 대해 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 미국, 영국, 남아프리카, 대한민국, 스위스 (리히텐슈타인 포함) 및 미국에 대 한 음성 및 연락처가 국가에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-132">For all teams, voicemail and contacts are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, Switzerland (includes Liechtenstein), and the United States.</span></span> <span data-ttu-id="ba537-133">다른 모든 국가의 경우 파일은 테 넌 트 선호도에 따라 미국, 유럽 또는 아시아 태평양 장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-133">For all other countries, files are stored in the US, Europe, or Asia-Pacific location based on tenant affinity.</span></span>

#### <a name="images-and-media"></a><span data-ttu-id="ba537-134">이미지 및 미디어</span><span class="sxs-lookup"><span data-stu-id="ba537-134">Images and media</span></span>

<span data-ttu-id="ba537-135">채팅에 사용 되는 미디어 (저장 되지 않고 원본 Giphy 서비스 URL에 대 한 참조 링크 인 Giphy Gif는 제외)는 채팅 서비스와 같은 위치에 배포 된 Azure 기반 미디어 서비스에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-135">Media used in chats (except for Giphy GIFs which aren't stored but are a reference link to the original Giphy service URL, Giphy is a non-Microsoft service) is stored in an Azure-based media service that is deployed to the same locations as the chat service.</span></span>

#### <a name="files"></a><span data-ttu-id="ba537-136">파일</span><span class="sxs-lookup"><span data-stu-id="ba537-136">Files</span></span>

<span data-ttu-id="ba537-137">채널의 누군가가 공유 하는 파일 (OneNote 및 위 키 포함)이 팀의 SharePoint 사이트에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-137">Files (including OneNote and Wiki) that somebody shares in a channel are stored in the team’s SharePoint site.</span></span> <span data-ttu-id="ba537-138">개인 채팅 또는 모임 또는 통화 중에 공유 된 파일은 파일을 공유 하는 사용자의 비즈니스 계정에 대 한 OneDrive에 업로드 되 고 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-138">Files shared in a private chat or a chat during a meeting or call are uploaded and stored in the OneDrive for the Business account of the user who shares the file.</span></span> <span data-ttu-id="ba537-139">Exchange, SharePoint 및 OneDrive는 전세계의 모든 데이터 센터 geos에서 데이터 영주권를 이미 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-139">Exchange, SharePoint and OneDrive already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="ba537-140">따라서 기존 고객의 경우 팀 환경의 일부인 모든 파일, OneNote 전자 필기장, 팀 위 키 내용, 사서함,이 테 넌 트 선호도에 따라 위치에 이미 저장 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-140">So, for existing customers, all files, OneNote notebooks, Teams wiki content, and mailboxes that are part of the Teams experience are already stored in the location based on your tenant affinity.</span></span> <span data-ttu-id="ba537-141">파일은 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 미국, 영국, 남아프리카, 대한민국, 스위스 (리히텐슈타인 포함)로 국가별에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-141">Files are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, and Switzerland (which includes Liechtenstein).</span></span> <span data-ttu-id="ba537-142">다른 모든 국가의 경우 파일은 테 넌 트 선호도에 따라 미국, 유럽 또는 아시아 태평양 장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-142">For all other countries, files are stored in the US, Europe, or Asia Pacific location based on tenant affinity.</span></span>

### <a name="datacenter-locations"></a><span data-ttu-id="ba537-143">데이터 센터 위치</span><span class="sxs-lookup"><span data-stu-id="ba537-143">Datacenter locations</span></span>

<span data-ttu-id="ba537-144">이 섹션에 설명 된 팀 서비스는 다음 위치에 나머지 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-144">The Teams services described in this section store data at rest in the following locations:</span></span>

|<span data-ttu-id="ba537-145">국가 또는 지역</span><span class="sxs-lookup"><span data-stu-id="ba537-145">Country or region</span></span>  |<span data-ttu-id="ba537-146">데이터 센터 위치</span><span class="sxs-lookup"><span data-stu-id="ba537-146">Datacenter location</span></span> |
|---------|---------|
|<span data-ttu-id="ba537-147">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="ba537-147">Australia</span></span>   |<span data-ttu-id="ba537-148">새로운 남아프리카 웨일스 및 Victoria</span><span class="sxs-lookup"><span data-stu-id="ba537-148">New South Wales and Victoria</span></span>         |
|<span data-ttu-id="ba537-149">캐나다</span><span class="sxs-lookup"><span data-stu-id="ba537-149">Canada</span></span>    |<span data-ttu-id="ba537-150">퀘벡에서 구/군/시</span><span class="sxs-lookup"><span data-stu-id="ba537-150">Quebec City and Toronto</span></span>         |
|<span data-ttu-id="ba537-151">프랑스</span><span class="sxs-lookup"><span data-stu-id="ba537-151">France</span></span>    |<span data-ttu-id="ba537-152">Marseille 및 파리</span><span class="sxs-lookup"><span data-stu-id="ba537-152">Marseille and Paris</span></span>         |
|<span data-ttu-id="ba537-153">독일</span><span class="sxs-lookup"><span data-stu-id="ba537-153">Germany</span></span>    |<span data-ttu-id="ba537-154">베를린 및 Frankfurt</span><span class="sxs-lookup"><span data-stu-id="ba537-154">Berlin and Frankfurt</span></span>      |
|<span data-ttu-id="ba537-155">인도</span><span class="sxs-lookup"><span data-stu-id="ba537-155">India</span></span>   |<span data-ttu-id="ba537-156">Chennai 및 Pune</span><span class="sxs-lookup"><span data-stu-id="ba537-156">Chennai and Pune</span></span>        |
|<span data-ttu-id="ba537-157">일본</span><span class="sxs-lookup"><span data-stu-id="ba537-157">Japan</span></span>    |<span data-ttu-id="ba537-158">도쿄 (Saitama) 및 오사카</span><span class="sxs-lookup"><span data-stu-id="ba537-158">Tokyo (Saitama) and Osaka</span></span>         |
|<span data-ttu-id="ba537-159">리히텐슈타인</span><span class="sxs-lookup"><span data-stu-id="ba537-159">Liechtenstein</span></span>   |<span data-ttu-id="ba537-160">Geneva 및 Zurich</span><span class="sxs-lookup"><span data-stu-id="ba537-160">Geneva and Zurich</span></span>       |
|<span data-ttu-id="ba537-161">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="ba537-161">South Africa</span></span>     |<span data-ttu-id="ba537-162">요하네스버그 및 카보베르데</span><span class="sxs-lookup"><span data-stu-id="ba537-162">Johannesburg and Cape Town</span></span>         |
|<span data-ttu-id="ba537-163">대한민국</span><span class="sxs-lookup"><span data-stu-id="ba537-163">South Korea</span></span>     |<span data-ttu-id="ba537-164">서울 및 Busan</span><span class="sxs-lookup"><span data-stu-id="ba537-164">Seoul and Busan</span></span>         |
|<span data-ttu-id="ba537-165">스위스</span><span class="sxs-lookup"><span data-stu-id="ba537-165">Switzerland</span></span>    |<span data-ttu-id="ba537-166">Geneva 및 Zurich</span><span class="sxs-lookup"><span data-stu-id="ba537-166">Geneva and Zurich</span></span>       |
|<span data-ttu-id="ba537-167">아랍 에미리트 연합국</span><span class="sxs-lookup"><span data-stu-id="ba537-167">United Arab Emirates</span></span>     |<span data-ttu-id="ba537-168">아부다비 및 두바이</span><span class="sxs-lookup"><span data-stu-id="ba537-168">Abu Dhabi and Dubai</span></span>         |
|<span data-ttu-id="ba537-169">영국</span><span class="sxs-lookup"><span data-stu-id="ba537-169">United Kingdom</span></span>     | <span data-ttu-id="ba537-170">Cardiff 및 런던</span><span class="sxs-lookup"><span data-stu-id="ba537-170">Cardiff and London</span></span>        |
|<span data-ttu-id="ba537-171">미주-북쪽 및 남부 (AMER)</span><span class="sxs-lookup"><span data-stu-id="ba537-171">Americas – North, and South (AMER)</span></span> |<span data-ttu-id="ba537-172">베이, CA, Boydton, VA</span><span class="sxs-lookup"><span data-stu-id="ba537-172">Bay, CA and Boydton, VA</span></span>       |
|<span data-ttu-id="ba537-173">아시아 태평양 (APAC)</span><span class="sxs-lookup"><span data-stu-id="ba537-173">Asia Pacific (APAC)</span></span>  |<span data-ttu-id="ba537-174">싱가포르 및 홍콩 특별 행정구</span><span class="sxs-lookup"><span data-stu-id="ba537-174">Singapore and Hong Kong</span></span>        |
|<span data-ttu-id="ba537-175">유럽/중동, 아시아 (EMEA)</span><span class="sxs-lookup"><span data-stu-id="ba537-175">Europe, Middle East, and Asia (EMEA)</span></span>   |<span data-ttu-id="ba537-176">더블린 및 암스테르담</span><span class="sxs-lookup"><span data-stu-id="ba537-176">Dublin and Amsterdam</span></span>        |

> [!NOTE]
> <span data-ttu-id="ba537-177">리히텐슈타인의 경우 데이터는 Geneva 및 Zurich의 스위스 데이터 센터에 나머지 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-177">For Liechtenstein, data is stored at rest in the Switzerland data centers in Geneva and Zurich.</span></span>

### <a name="data-stored-with-a-third-party-storage-provider"></a><span data-ttu-id="ba537-178">타사 저장소 공급자에 저장 된 데이터</span><span class="sxs-lookup"><span data-stu-id="ba537-178">Data stored with a third-party storage provider</span></span>

<span data-ttu-id="ba537-179">타사 저장소 공급자를 사용 하 여 파일을 저장할 수 있도록 허용 하는 조직은 해당 서비스의 저장소 위치에 따라 달라 지므로 해당 서비스에 대 한 나머지 데이터 위치를 별도로 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-179">Organizations who allow users to store files with a third-party storage provider are dependent on the storage location of those services and should, therefore, review the location of data at rest for those services separately.</span></span>

- <span data-ttu-id="ba537-180">**탭**: 탭을 통해 사용자는 앱 및 서비스에서 채널에 정보를 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-180">**Tabs**: Tabs allow users to pin information from apps and services to a channel.</span></span> <span data-ttu-id="ba537-181">따라서 데이터는 저장 된 탭의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-181">Thus, it varies by type of the tab where the data is stored.</span></span> <span data-ttu-id="ba537-182">탭 자체에는 데이터가 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-182">The tab itself doesn't store any data.</span></span> <span data-ttu-id="ba537-183">예를 들어 SharePoint 탭은 SharePoint 사이트 컬렉션이 프로 비전 된 위치에 따라 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-183">For example, a SharePoint tab will store data based on where the SharePoint site collection was provisioned.</span></span> <span data-ttu-id="ba537-184">파트너의 정보를 포함 하는 탭은 파트너가 사용 하는 시스템에 데이터를 직접 저장 하 고 보기만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-184">A tab that includes information from a partner will store the data directly in the system used by the partner and only present a view of it.</span></span>
- <span data-ttu-id="ba537-185">**다른 파트너 앱**: Microsoft는 팀 경험 내에서 사용할 수 있는 파트너의 앱 및 서비스에 대 한 데이터 영주권 지원 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-185">**Other partner apps**: Microsoft doesn't provide any data residency support for apps and services from partners that you might be using within the Teams experience.</span></span> <span data-ttu-id="ba537-186">해당 솔루션의 정보를 직접 검토 하 여 데이터가 저장 되는 위치를 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-186">Review information from those solutions directly to learn about where their data is being stored.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba537-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba537-187">See also</span></span>

- [<span data-ttu-id="ba537-188">Microsoft 팀이 미국 아랍 데이터 영주권을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-188">Microsoft Teams launches United Arab Emirates Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [<span data-ttu-id="ba537-189">Microsoft 팀이 동남 영주권 데이터를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-189">Microsoft Teams launches South Korean Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [<span data-ttu-id="ba537-190">Microsoft 팀이 남아프리카 데이터 영주권을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-190">Microsoft Teams launches South African Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [<span data-ttu-id="ba537-191">Microsoft 팀이 프랑스 데이터 영주권을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-191">Microsoft Teams Launches France Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [<span data-ttu-id="ba537-192">Microsoft 팀은 인도 데이터 영주권를 시작 하 고 다른 geos는 곧 출시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-192">Microsoft Teams launches India Data Residency, other geos coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [<span data-ttu-id="ba537-193">Microsoft 팀이 오스트레일리아와 일본 데이터 영주권을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba537-193">Microsoft Teams Launches Australia and Japan Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [<span data-ttu-id="ba537-194">Microsoft 팀은 캐나다 데이터 영주권, 오스트레일리아 및 일본 출시 예정</span><span class="sxs-lookup"><span data-stu-id="ba537-194">Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
