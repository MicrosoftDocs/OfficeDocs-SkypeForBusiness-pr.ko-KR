---
title: 비즈니스용 Skype에서 Mac 클라이언트 환경 사용자 지정
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: 이 문서에서는 Mac의 비즈니스용 Skype 클라이언트에 사용할 수 있는 클라이언트 기본 설정 및 기본값과 앱 외부에서 이를 편집하는 방법을 설명합니다.
ms.openlocfilehash: cdbd1c109fffddf6d922657285f60d9b4f06924a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805758"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="04694-103">비즈니스용 Skype에서 Mac 클라이언트 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="04694-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="04694-104">이 문서에서는 Mac의 비즈니스용 Skype 클라이언트에 사용할 수 있는 클라이언트 기본 설정 및 기본값과 앱 외부에서 이를 편집하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04694-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="04694-105">Mac의 비즈니스용 Skype 클라이언트 기본 설정</span><span class="sxs-lookup"><span data-stu-id="04694-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="04694-106">Mac용 비즈니스용 Skype 클라이언트에서 사용할 수 있는 특정 기능 및 동작은 클라이언트의 기본 설정에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="04694-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="04694-107">Mac의 비즈니스용 Skype 기본 설정은 다음 경로에 있는 비즈니스용 Skype 클라이언트를 설치한 Mac에 있는 파일에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04694-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="04694-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="04694-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="04694-109">이러한 기본 설정을 설정하려면 클라이언트의 Mac에서 터미널 프롬프트로 이동하고 필요한 경우 다음 표에 설명된 기본 설정 키를 사용하여 기본값 쓰기 com.microsoft.SkypeForBusiness 키 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04694-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="04694-110">**클라이언트 기본 설정 키**</span><span class="sxs-lookup"><span data-stu-id="04694-110">**Client preference keys**</span></span>


| <span data-ttu-id="04694-111">키</span><span class="sxs-lookup"><span data-stu-id="04694-111">Key</span></span> | <span data-ttu-id="04694-112">유형</span><span class="sxs-lookup"><span data-stu-id="04694-112">Type</span></span> | <span data-ttu-id="04694-113">값</span><span class="sxs-lookup"><span data-stu-id="04694-113">Value</span></span> | <span data-ttu-id="04694-114">설명</span><span class="sxs-lookup"><span data-stu-id="04694-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04694-115">autoDetectAutoDicoveryURLs</span><span class="sxs-lookup"><span data-stu-id="04694-115">autoDetectAutoDicoveryURLs</span></span>    |<span data-ttu-id="04694-116">Bool</span><span class="sxs-lookup"><span data-stu-id="04694-116">Bool</span></span>    |<span data-ttu-id="04694-117">0 = 수동 서버 구성</span><span class="sxs-lookup"><span data-stu-id="04694-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="04694-118">1 = 자동 서버 검색(기본값)</span><span class="sxs-lookup"><span data-stu-id="04694-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="04694-119">비즈니스용 Skype에서 로그인 중에 전송 및 서버를 식별하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04694-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="04694-120">이 정책 설정을 사용하면 **internalAutoDiscoveryURL** 및 **externalAutoDiscoveryURL을 지정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="04694-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="04694-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="04694-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="04694-122">문자열</span><span class="sxs-lookup"><span data-stu-id="04694-122">String</span></span>    |<span data-ttu-id="04694-123">전체 자동iscover URL</span><span class="sxs-lookup"><span data-stu-id="04694-123">Full autodiscover URL</span></span>    |<span data-ttu-id="04694-124">내부 자동iscover URL</span><span class="sxs-lookup"><span data-stu-id="04694-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="04694-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="04694-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="04694-126">문자열</span><span class="sxs-lookup"><span data-stu-id="04694-126">String</span></span>    |<span data-ttu-id="04694-127">전체 자동iscover URL</span><span class="sxs-lookup"><span data-stu-id="04694-127">Full autodiscover URL</span></span>    |<span data-ttu-id="04694-128">외부 자동iscover URL</span><span class="sxs-lookup"><span data-stu-id="04694-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="04694-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="04694-129">httpProxyDomain</span></span>    |<span data-ttu-id="04694-130">문자열</span><span class="sxs-lookup"><span data-stu-id="04694-130">String</span></span>    ||<span data-ttu-id="04694-131">HTTP 프록시 도메인</span><span class="sxs-lookup"><span data-stu-id="04694-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="04694-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="04694-132">httpProxyUserName</span></span>    |<span data-ttu-id="04694-133">문자열</span><span class="sxs-lookup"><span data-stu-id="04694-133">String</span></span>    ||<span data-ttu-id="04694-134">HTTP 프록시 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="04694-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="04694-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="04694-135">httpProxyPassword</span></span>    |<span data-ttu-id="04694-136">문자열</span><span class="sxs-lookup"><span data-stu-id="04694-136">String</span></span>    ||<span data-ttu-id="04694-137">HTTP 프록시 암호</span><span class="sxs-lookup"><span data-stu-id="04694-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="04694-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="04694-138">trustedDomainList</span></span>    |<span data-ttu-id="04694-139">배열</span><span class="sxs-lookup"><span data-stu-id="04694-139">Array</span></span>    ||<span data-ttu-id="04694-140">HTTP 리디렉션을 위한 신뢰할 수 있는 도메인 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="04694-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="04694-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="04694-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="04694-142">숫자</span><span class="sxs-lookup"><span data-stu-id="04694-142">Number</span></span>    |<span data-ttu-id="04694-143">300(기본값)</span><span class="sxs-lookup"><span data-stu-id="04694-143">300 (default)</span></span>    |<span data-ttu-id="04694-144">서버 쪽 대화 기록이 없는 사용자의 자동 수락 시간 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="04694-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="04694-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="04694-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="04694-146">Bool</span><span class="sxs-lookup"><span data-stu-id="04694-146">Bool</span></span>    |<span data-ttu-id="04694-147">0 = 사용 안</span><span class="sxs-lookup"><span data-stu-id="04694-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="04694-148">1 = 사용</span><span class="sxs-lookup"><span data-stu-id="04694-148">1 = Enabled</span></span>    |<span data-ttu-id="04694-149">알 수 없는 위치에서 긴급 번호로 전화를 걸 때 사용자에게 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="04694-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="04694-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="04694-150">sipAddress</span></span>    |<span data-ttu-id="04694-151">문자열</span><span class="sxs-lookup"><span data-stu-id="04694-151">String</span></span>    ||<span data-ttu-id="04694-152">비즈니스용 Skype에 로그인하는 데 사용되는 SIP 주소(전자 메일)입니다.</span><span class="sxs-lookup"><span data-stu-id="04694-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="04694-153">userName</span><span class="sxs-lookup"><span data-stu-id="04694-153">userName</span></span>    |<span data-ttu-id="04694-154">문자열</span><span class="sxs-lookup"><span data-stu-id="04694-154">String</span></span>    ||<span data-ttu-id="04694-155">비즈니스용 Skype에 로그인하는 데 사용되는 UPN(UserName)입니다.</span><span class="sxs-lookup"><span data-stu-id="04694-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="04694-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="04694-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="04694-157">Bool</span><span class="sxs-lookup"><span data-stu-id="04694-157">Bool</span></span>    |<span data-ttu-id="04694-158">0 = 기본 로그인 화면 및 고급 속성 대화 상자에 사용자 이름 필드 표시</span><span class="sxs-lookup"><span data-stu-id="04694-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="04694-159">1 = 고급 속성 대화 상자에만 사용자 이름 필드 표시(기본값)</span><span class="sxs-lookup"><span data-stu-id="04694-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="04694-160">로그인하는 동안 사용자 이름 필드가 표시되는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04694-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="04694-161">사용 예제</span><span class="sxs-lookup"><span data-stu-id="04694-161">Usage examples</span></span>

<span data-ttu-id="04694-162">신뢰할 수 있는 도메인 목록에 단일 도메인(Contoso.com)을 추가하려면 다음과 같이 trustedDomainList 키를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04694-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="04694-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span><span class="sxs-lookup"><span data-stu-id="04694-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="04694-164">신뢰할 수 있는 도메인 목록에 여러 도메인을 추가하려면 다음과 같이 trustedDomainList 키를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04694-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="04694-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span><span class="sxs-lookup"><span data-stu-id="04694-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="04694-166">샘플의 기본 설정</span><span class="sxs-lookup"><span data-stu-id="04694-166">Sample unedited settings</span></span>

<span data-ttu-id="04694-167">참조를 위해 다음은 기본 설정만 사용하는 샘플 설정 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="04694-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
```console
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
