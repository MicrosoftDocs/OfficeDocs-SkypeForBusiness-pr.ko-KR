---
title: 비즈니스용 Skype에서 Mac 클라이언트 환경 사용자 지정
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: 이 문서에서는 Mac 클라이언트의 비즈니스용 Skype에서 사용할 수 있는 클라이언트 기본 설정 및 기본값과 앱 외부에서이를 편집 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: fa9b809c742a87a7f522ed211406e2b97cbcfe6d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189585"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="53d60-103">비즈니스용 Skype에서 Mac 클라이언트 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="53d60-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="53d60-104">이 문서에서는 Mac 클라이언트의 비즈니스용 Skype에서 사용할 수 있는 클라이언트 기본 설정 및 기본값과 앱 외부에서이를 편집 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="53d60-105">Mac 용 비즈니스용 Skype 클라이언트 기본 설정</span><span class="sxs-lookup"><span data-stu-id="53d60-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="53d60-106">Mac 클라이언트의 비즈니스용 Skype에서 사용할 수 있는 특정 기능 및 동작은 클라이언트의 기본 설정에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="53d60-107">Mac의 비즈니스용 Skype 기본 설정은 다음 경로에 있는 비즈니스용 Skype 클라이언트를 설치한 Mac에 있는 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="53d60-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="53d60-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="53d60-109">이러한 기본 설정을 지정 하려면, 필요한 경우 클라이언트의 Mac에서 터미널 프롬프트로 이동 하 고, 다음 표에 설명 된 기본 설정 키를 사용 하 여 입력 키 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="53d60-110">**클라이언트 기본 설정 키**</span><span class="sxs-lookup"><span data-stu-id="53d60-110">**Client preference keys**</span></span>


| <span data-ttu-id="53d60-111">키</span><span class="sxs-lookup"><span data-stu-id="53d60-111">Key</span></span> | <span data-ttu-id="53d60-112">유형</span><span class="sxs-lookup"><span data-stu-id="53d60-112">Type</span></span> | <span data-ttu-id="53d60-113">값</span><span class="sxs-lookup"><span data-stu-id="53d60-113">Value</span></span> | <span data-ttu-id="53d60-114">설명</span><span class="sxs-lookup"><span data-stu-id="53d60-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="53d60-115">AutoDetectAutoDiscoveryURLs</span><span class="sxs-lookup"><span data-stu-id="53d60-115">AutoDetectAutoDiscoveryURLs</span></span>    |<span data-ttu-id="53d60-116">부울</span><span class="sxs-lookup"><span data-stu-id="53d60-116">Bool</span></span>    |<span data-ttu-id="53d60-117">0 = 수동 서버 구성</span><span class="sxs-lookup"><span data-stu-id="53d60-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="53d60-118">1 = 자동 서버 검색 (기본값)</span><span class="sxs-lookup"><span data-stu-id="53d60-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="53d60-119">비즈니스용 Skype에서 로그인 중에 사용할 전송 및 서버를 식별 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="53d60-120">이 정책 설정을 사용 하도록 설정 하는 경우 **internalautodiscoveryurl** 및 **externalautodiscoveryurl**을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="53d60-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="53d60-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="53d60-122">문자열</span><span class="sxs-lookup"><span data-stu-id="53d60-122">String</span></span>    |<span data-ttu-id="53d60-123">전체 자동 검색 URL</span><span class="sxs-lookup"><span data-stu-id="53d60-123">Full autodiscover URL</span></span>    |<span data-ttu-id="53d60-124">내부 자동 검색 URL</span><span class="sxs-lookup"><span data-stu-id="53d60-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="53d60-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="53d60-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="53d60-126">문자열</span><span class="sxs-lookup"><span data-stu-id="53d60-126">String</span></span>    |<span data-ttu-id="53d60-127">전체 자동 검색 URL</span><span class="sxs-lookup"><span data-stu-id="53d60-127">Full autodiscover URL</span></span>    |<span data-ttu-id="53d60-128">외부 자동 검색 URL</span><span class="sxs-lookup"><span data-stu-id="53d60-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="53d60-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="53d60-129">httpProxyDomain</span></span>    |<span data-ttu-id="53d60-130">문자열</span><span class="sxs-lookup"><span data-stu-id="53d60-130">String</span></span>    ||<span data-ttu-id="53d60-131">HTTP 프록시 도메인</span><span class="sxs-lookup"><span data-stu-id="53d60-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="53d60-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="53d60-132">httpProxyUserName</span></span>    |<span data-ttu-id="53d60-133">문자열</span><span class="sxs-lookup"><span data-stu-id="53d60-133">String</span></span>    ||<span data-ttu-id="53d60-134">HTTP 프록시 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="53d60-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="53d60-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="53d60-135">httpProxyPassword</span></span>    |<span data-ttu-id="53d60-136">문자열</span><span class="sxs-lookup"><span data-stu-id="53d60-136">String</span></span>    ||<span data-ttu-id="53d60-137">HTTP 프록시 암호</span><span class="sxs-lookup"><span data-stu-id="53d60-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="53d60-138">(도메인) 주소록</span><span class="sxs-lookup"><span data-stu-id="53d60-138">trustedDomainList</span></span>    |<span data-ttu-id="53d60-139">배열의</span><span class="sxs-lookup"><span data-stu-id="53d60-139">Array</span></span>    ||<span data-ttu-id="53d60-140">HTTP 리디렉션에 대 한 신뢰할 수 있는 도메인 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="53d60-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="53d60-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="53d60-142">숫자로</span><span class="sxs-lookup"><span data-stu-id="53d60-142">Number</span></span>    |<span data-ttu-id="53d60-143">300 (기본값)</span><span class="sxs-lookup"><span data-stu-id="53d60-143">300 (default)</span></span>    |<span data-ttu-id="53d60-144">서버 쪽 대화 기록이 없는 사용자에 대 한 자동 수락 시간 제한을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="53d60-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="53d60-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="53d60-146">부울</span><span class="sxs-lookup"><span data-stu-id="53d60-146">Bool</span></span>    |<span data-ttu-id="53d60-147">0 = 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="53d60-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="53d60-148">1 = 사용</span><span class="sxs-lookup"><span data-stu-id="53d60-148">1 = Enabled</span></span>    |<span data-ttu-id="53d60-149">알 수 없는 위치에서 비상 번호로 전화를 걸 때 사용자에 게 경고를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="53d60-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="53d60-150">sipAddress</span></span>    |<span data-ttu-id="53d60-151">문자열</span><span class="sxs-lookup"><span data-stu-id="53d60-151">String</span></span>    ||<span data-ttu-id="53d60-152">비즈니스용 Skype에 로그인 하는 데 사용 되는 SIP 주소 (전자 메일)입니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="53d60-153">사용자</span><span class="sxs-lookup"><span data-stu-id="53d60-153">userName</span></span>    |<span data-ttu-id="53d60-154">문자열</span><span class="sxs-lookup"><span data-stu-id="53d60-154">String</span></span>    ||<span data-ttu-id="53d60-155">비즈니스용 Skype에 로그인 하는 데 사용 되는 UPN (사용자 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="53d60-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="53d60-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="53d60-157">부울</span><span class="sxs-lookup"><span data-stu-id="53d60-157">Bool</span></span>    |<span data-ttu-id="53d60-158">0 = 기본 로그인 화면 및 고급 속성 대화 상자에서 사용자 이름 필드 표시</span><span class="sxs-lookup"><span data-stu-id="53d60-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="53d60-159">1 = 고급 속성 대화 상자에만 사용자 이름 필드 표시 (기본값)</span><span class="sxs-lookup"><span data-stu-id="53d60-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="53d60-160">로그인 중에 사용자 이름 필드가 표시 되는 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="53d60-161">사용 예제</span><span class="sxs-lookup"><span data-stu-id="53d60-161">Usage examples</span></span>

<span data-ttu-id="53d60-162">신뢰할 수 있는 도메인 목록에 단일 도메인 (Contoso.com)을 추가 하려면 다음과 같이 트러스트 된 Domainlist 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="53d60-163">기본값은 com을 작성 합니다. 입력 Contoso.com Domainlist-array-""를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="53d60-164">신뢰할 수 있는 도메인 목록에 여러 도메인을 추가 하려면 다음과 같이 트러스트 된 Domainlist 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="53d60-165">기본값으로 com을 작성 합니다. 입력 sfb.com "" "" abc.com "" test.org "를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="53d60-166">샘플 편집 안 한 설정</span><span class="sxs-lookup"><span data-stu-id="53d60-166">Sample unedited settings</span></span>

<span data-ttu-id="53d60-167">참조용으로 기본 설정만 사용 하는 샘플 설정 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53d60-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
```
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
