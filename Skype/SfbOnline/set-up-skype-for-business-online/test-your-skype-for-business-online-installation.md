---
title: 비즈니스용 Skype Online 설치 테스트
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 19873b1f-8f7e-4dd8-92f4-2ce11344ed5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '테스트 계정 및 컴퓨터를 설정하고 전화 접속 회의, 개인 간 통화, 회의 및 로그인과 같은 온라인 기능을 테스트하여 시간을 절약하고, 통화를 지원하고 만족도를 높이는 방법을 알아보는 방법을 배워 보십시오. '
ms.openlocfilehash: 378fe1ad980de5c28c9175cf7e1e918b580c257a
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239519"
---
# <a name="test-your-skype-for-business-online-installation"></a><span data-ttu-id="2f0c4-103">비즈니스용 Skype Online 설치 테스트</span><span class="sxs-lookup"><span data-stu-id="2f0c4-103">Test your Skype for Business Online installation</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="2f0c4-104">조직의 모든 사용자에 대해 설치하기 전에 비즈니스용 Skype 온라인 설치를 테스트하여 시간을 절약하고 지원 호출을 줄이고 사용자 만족도를 높입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-104">Save time, reduce support calls, and increase user satisfaction by testing your Skype for Business Online installation before you set it up for everyone in your organization.</span></span>

<span data-ttu-id="2f0c4-105">필요한 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-105">Here's what you need:</span></span>

- <span data-ttu-id="2f0c4-106">계정 또는 Microsoft 365 Office 365 계정(사용자 및 Office 365 이상)입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-106">At least three Microsoft 365 or Office 365 accounts (yours and at least two others).</span></span>

- <span data-ttu-id="2f0c4-107">각 테스트 계정에 대한 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-107">A computer for each test account.</span></span> <span data-ttu-id="2f0c4-108">조직에 있는 일반적인 컴퓨터처럼 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-108">Set them up like a typical computer would be in your organization.</span></span>

- <span data-ttu-id="2f0c4-109">온라인용 오디오 회의 공급자가 비즈니스용 Skype 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-109">An account with an audio conferencing provider for Skype for Business Online.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="2f0c4-110">무슨 작업을 수행하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="2f0c4-110">What do you want to do?</span></span>

> [<span data-ttu-id="2f0c4-111">테스트 계정 설정</span><span class="sxs-lookup"><span data-stu-id="2f0c4-111">Set up test accounts</span></span>](test-your-skype-for-business-online-installation.md#__toc328126910)
> 
> [<span data-ttu-id="2f0c4-112">테스트 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="2f0c4-112">Set up test computers</span></span>](test-your-skype-for-business-online-installation.md#__toc328126911)
> 
> [<span data-ttu-id="2f0c4-113">오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="2f0c4-113">Set up Audio Conferencing</span></span>](test-your-skype-for-business-online-installation.md#__toc328126912)
> 
> [<span data-ttu-id="2f0c4-114">온라인 비즈니스용 Skype 및 디바이스 테스트</span><span class="sxs-lookup"><span data-stu-id="2f0c4-114">Test Skype for Business Online features and devices</span></span>](test-your-skype-for-business-online-installation.md#__toc328126913)

## <a name="set-up-test-accounts"></a><span data-ttu-id="2f0c4-115">테스트 계정 설정</span><span class="sxs-lookup"><span data-stu-id="2f0c4-115">Set up test accounts</span></span>
<span data-ttu-id="2f0c4-116"><a name="__toc328126910"> </a></span><span class="sxs-lookup"><span data-stu-id="2f0c4-116"><a name="__toc328126910"> </a></span></span>

1. <span data-ttu-id="2f0c4-117">관리자 **Microsoft 365** 또는 Office 365 그룹으로 이동한 다음 추가를 선택하고 필요한 정보를  >     >   ![ ](../images/328ffb57-5f31-430a-b653-4a6b8e76d338.png) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-117">Go to **Admin** > **Microsoft 365** or **Office 365** > **Users and groups**, and then select add![Add](../images/328ffb57-5f31-430a-b653-4a6b8e76d338.png) and enter the required information.</span></span>

2. <span data-ttu-id="2f0c4-118">4단계(전자 메일)에 오면 사용자 자신의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-118">When you come to Step 4 (Email), enter your own email address.</span></span> <span data-ttu-id="2f0c4-119">그러면 새 사용자의 이름 및 암호에 대한 레코드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-119">You'll then have a record of the new user's name and password.</span></span>

3. <span data-ttu-id="2f0c4-120">원하는 테스트 계정 수가 될 때까지 1단계와 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-120">Repeat steps 1 and 2 until you have the number of test accounts you want.</span></span> <span data-ttu-id="2f0c4-121">온라인 모임의 온라인 모임 기능을 테스트하려면 두 개 이상의 계정이 비즈니스용 Skype 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-121">You need at least two accounts (besides your own) to test the online meeting capabilities of Skype for Business Online.</span></span>

## <a name="set-up-test-computers"></a><span data-ttu-id="2f0c4-122">테스트 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="2f0c4-122">Set up test computers</span></span>
<span data-ttu-id="2f0c4-123"><a name="__toc328126911"> </a></span><span class="sxs-lookup"><span data-stu-id="2f0c4-123"><a name="__toc328126911"> </a></span></span>

<span data-ttu-id="2f0c4-124">각 테스트 컴퓨터에서:</span><span class="sxs-lookup"><span data-stu-id="2f0c4-124">On each test computer:</span></span>

1. <span data-ttu-id="2f0c4-125">웹 Microsoft 365 또는 Office 365 페이지로 이동하고 테스트 계정 중 하나에서 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-125">Go to the Microsoft 365 or Office 365 home page and sign in with credentials from one of your test accounts.</span></span>

2. <span data-ttu-id="2f0c4-126">설정 설정: 프로필을 업데이트하고, 소프트웨어를 설치하고 클라우드에 연결한 다음 소프트웨어 설치를 클릭하고 클라우드에 ![ ](../images/4b83e9cb-c7e4-46c8-b3d1-cfee017123ae.png) **연결합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-126">Go to **Settings**![Settings: update your profile, install software and connect it to the cloud](../images/4b83e9cb-c7e4-46c8-b3d1-cfee017123ae.png), and then click **Install software and connect it to the cloud**.</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="2f0c4-127">오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="2f0c4-127">Set up Audio Conferencing</span></span>
<span data-ttu-id="2f0c4-128"><a name="__toc328126912"> </a></span><span class="sxs-lookup"><span data-stu-id="2f0c4-128"><a name="__toc328126912"> </a></span></span>

<span data-ttu-id="2f0c4-129">온라인 모임에 비즈니스용 Skype 전화 액세스를 제공하려면 오디오 회의 공급자를 통해 계정을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-129">To provide telephone access to Skype for Business Online meetings, set up an account with an audio conferencing provider.</span></span> <span data-ttu-id="2f0c4-130">다음은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-130">Here's what you get:</span></span>

- <span data-ttu-id="2f0c4-131">사용 가능한 경우 전화 접속 번호 및 무료 전화 번호.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-131">Toll dial-in numbers, and toll-free numbers if available.</span></span>

- <span data-ttu-id="2f0c4-132">모임을 예약하거나 리드하는 조직의 각 사용자에 대해 회의 코드 및 PIN(개인 식별 번호)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-132">For each user in your organization who schedules or leads meetings, a conference code and personal identification number (PIN).</span></span>

<span data-ttu-id="2f0c4-133">오디오 회의를 위해 사용자를 설정한 후 전화 접속 번호 및 회의 코드가 있는 자동화된 전자 메일 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-133">After setting up your users for audio conferencing, they receive an automated email message with the dial-in numbers and conference code.</span></span> <span data-ttu-id="2f0c4-134">이 정보는 새 모임 요청에 비즈니스용 Skype 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-134">This information is also automatically added to new Skype for Business meeting requests.</span></span>

 <span data-ttu-id="2f0c4-135">**테스트 사용자 중 하나의 계정에 오디오 회의 정보를 추가하려면**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-135">**To add audio conferencing information to the account of one of your test users**</span></span>

1. <span data-ttu-id="2f0c4-136">오디오 회의 사용자 **를**  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-136">Click **Audio Conferencing** > **Users**.</span></span>

2. <span data-ttu-id="2f0c4-137">전화 접속 회의를 위해 설정할 사용자의 이름을 클릭한 다음 **편집을** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-137">Click the names of the users you want to set up for dial-in conferencing, and then click **Edit**![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>

3. <span data-ttu-id="2f0c4-138">오디오 회의 공급자를 선택하고 요청된 정보를 입력한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-138">Select your audio conferencing provider, type the requested information, and then click **Save**.</span></span>

|<span data-ttu-id="2f0c4-139">**오디오 회의 설정**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-139">**Audio conferencing setting**</span></span>|<span data-ttu-id="2f0c4-140">**설명**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2f0c4-141">**공급자**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-141">**Provider**</span></span> <br/> |<span data-ttu-id="2f0c4-142">목록에서 오디오 회의 공급자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-142">Choose your audio conferencing provider from the list.</span></span>  <br/> |
|<span data-ttu-id="2f0c4-143">**전화** 번호(필수)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-143">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="2f0c4-144">오디오 회의 공급자에서 받은 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-144">The phone numbers you received from the audio conferencing provider.</span></span> <span data-ttu-id="2f0c4-145">모임 초대에 표시하려는 비즈니스용 Skype 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-145">Format the numbers like you want them to appear in Skype for Business meeting invitations.</span></span>  <br/> |
|<span data-ttu-id="2f0c4-146">**무료 전화 번호**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-146">**Toll-free number**</span></span> <br/> |<span data-ttu-id="2f0c4-147">오디오 회의 공급자에서 받은 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-147">The phone numbers you received from the audio conferencing provider.</span></span> <span data-ttu-id="2f0c4-148">모임 초대에 표시하려는 비즈니스용 Skype 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-148">Format the numbers like you want them to appear in Skype for Business meeting invitations.</span></span>  <br/> |
|<span data-ttu-id="2f0c4-149">**암호**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-149">**Passcode**</span></span> <br/> |<span data-ttu-id="2f0c4-150">이 사용자에 대한 암호 또는 컨퍼런스 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-150">The passcode, or conference code, for this user.</span></span>  <br/> |

## <a name="test-skype-for-business-online-features-and-devices"></a><span data-ttu-id="2f0c4-151">온라인 비즈니스용 Skype 및 디바이스 테스트</span><span class="sxs-lookup"><span data-stu-id="2f0c4-151">Test Skype for Business Online features and devices</span></span>
<span data-ttu-id="2f0c4-152"><a name="__toc328126913"> </a></span><span class="sxs-lookup"><span data-stu-id="2f0c4-152"><a name="__toc328126913"> </a></span></span>

<span data-ttu-id="2f0c4-153">주요 비즈니스용 Skype 온라인 기능이 예상대로 작동하고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-153">Verify that the major Skype for Business Online features are working as expected.</span></span>

 <span data-ttu-id="2f0c4-154">**로그인 및 로그인**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-154">**Sign in and sign out**</span></span>

|<span data-ttu-id="2f0c4-155">**작업**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-155">**Task**</span></span>|<span data-ttu-id="2f0c4-156">**예상 결과**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-156">**Expected result**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2f0c4-157">Lync Online에 로그인 및 아웃</span><span class="sxs-lookup"><span data-stu-id="2f0c4-157">Sign in to and out of Lync Online</span></span>](https://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |<span data-ttu-id="2f0c4-158">로그인 비즈니스용 Skype 지정한 현재 상태와 함께 기본 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-158">The Skype for Business main window appears, with the presence state you specified when you signed in</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-159">Lync Online에 로그인 및 아웃</span><span class="sxs-lookup"><span data-stu-id="2f0c4-159">Sign in to and out of Lync Online</span></span>](https://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |<span data-ttu-id="2f0c4-160">비즈니스용 Skype 로그인 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-160">The Skype for Business sign-in screen is displayed</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-161">Lync Online에 로그인 및 아웃</span><span class="sxs-lookup"><span data-stu-id="2f0c4-161">Sign in to and out of Lync Online</span></span>](https://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |<span data-ttu-id="2f0c4-162">비즈니스용 Skype 창이 닫히고 비즈니스용 Skype 알림 영역에 더 이상 Windows 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-162">The Skype for Business window closes, and the Skype for Business icon no longer appears in the Windows notification area.</span></span>  <br/> |

<span data-ttu-id="2f0c4-163">로그인할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="2f0c4-163">Can't sign in?</span></span> <span data-ttu-id="2f0c4-164">온라인에서 로그인 문제를 해결하는 [비즈니스용 Skype 참조하세요.](https://support.microsoft.com/kb/2541980)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-164">See [How to troubleshoot sign-in issues in Skype for Business Online](https://support.microsoft.com/kb/2541980).</span></span>

 <span data-ttu-id="2f0c4-165">**연락처, 현재 상태 및 인스턴트 메시징**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-165">**Contacts, presence, and instant messaging**</span></span>

|<span data-ttu-id="2f0c4-166">**작업**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-166">**Task**</span></span>|<span data-ttu-id="2f0c4-167">**예상 결과**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-167">**Expected result**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2f0c4-168">IM을 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="2f0c4-168">Send an IM in Skype for Business</span></span>](https://support.office.com/article/b3aefb9b-dec8-4be8-a1ee-1eab12144d05) <br/> |<span data-ttu-id="2f0c4-169">대화 비즈니스용 Skype 창이 나타나면 입력하고, 연락한 사람의 응답이 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-169">The Skype for Business conversation window appears, you type something, and you receive a response from the person you contacted.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-170">IM을 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="2f0c4-170">Send an IM in Skype for Business</span></span>](https://support.office.com/article/b3aefb9b-dec8-4be8-a1ee-1eab12144d05) <br/> |<span data-ttu-id="2f0c4-171">대화 비즈니스용 Skype 창이 표시되어 입력하면 대화의 모든 사람이 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-171">The Skype for Business conversation window appears, you type something, and everyone in the conversation responds.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-172">이름 또는 성으로 연락처 검색</span><span class="sxs-lookup"><span data-stu-id="2f0c4-172">Search for a contact by using their first or last name</span></span>](https://support.office.live.com/article/29fa2061-f679-4e0d-902d-736b67774c8b#BKMK_ContactsFAQ) <br/> |<span data-ttu-id="2f0c4-173">입력을 시작하는 즉시 검색 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-173">Your search results begin to appear as soon as you start typing.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-174">Lync for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f0c4-174">FAQ about Lync for Microsoft 365</span></span>](https://support.office.com/article/29fa2061-f679-4e0d-902d-736b67774c8b.aspx#BKMK_ContactsFAQ) <br/> |<span data-ttu-id="2f0c4-175">추가한 연락처가 선택한 연락처 그룹에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-175">The contact you added appears in the Contacts group you chose.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-176">Lync에서 현재 상태 변경</span><span class="sxs-lookup"><span data-stu-id="2f0c4-176">Change your presence status in Lync</span></span>](https://support.office.com/article/ef8998cc-7801-4b62-81ba-9a2c1630f9e5) <br/> |<span data-ttu-id="2f0c4-177">새 현재 상태는 다른 사용자 연락처 목록에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-177">Your new presence status is reflected in other people's Contacts list.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-178">연락처 카드 사용</span><span class="sxs-lookup"><span data-stu-id="2f0c4-178">Use the contact card</span></span>](https://support.office.com/article/19870880-FC90-46B0-9C60-C398518E9FBC) <br/> |<span data-ttu-id="2f0c4-179">해당 사람의 연락처 카드가 이름 근처에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-179">The person's contact card appears near their name.</span></span>  <br/> |

 <span data-ttu-id="2f0c4-180">**대인 통화**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-180">**Person-to-person calls**</span></span>

|<span data-ttu-id="2f0c4-181">**작업**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-181">**Task**</span></span>|<span data-ttu-id="2f0c4-182">**예상 결과**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-182">**Expected result**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2f0c4-183">Lync 오디오 통화 만들기 및 수신</span><span class="sxs-lookup"><span data-stu-id="2f0c4-183">Make and receive a Lync audio call</span></span>](https://support.office.com/article/39342f16-4d16-44de-a806-0b2b566f3886) <br/> |<span data-ttu-id="2f0c4-184">대화 창이 나타나면 통화가 울립니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-184">The conversation window appears and you hear the call ringing.</span></span> <span data-ttu-id="2f0c4-185">통화하는 사람이 데스크톱 경고를 수신하고 전화를 수락하고 대화 창이 연결되면 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-185">The person you're calling receives a desktop alert and accepts the call, and the conversation window is updated when they're connected.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-186">Lync 인스턴트 메시지 대화에 오디오 추가</span><span class="sxs-lookup"><span data-stu-id="2f0c4-186">Add audio to a Lync instant message conversation</span></span>](https://support.office.com/article/21a098b2-63f1-4205-a9aa-532b6a67ea92) <br/> |<span data-ttu-id="2f0c4-187">통화가 연결되고 IM을 통해 다른 사용자와 대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-187">The call is connected and you can IM and talk with the other person.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-188">Lync에서 데스크톱 또는 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="2f0c4-188">Share your desktop or a program in Lync</span></span>](https://support.office.com/article/33aaa965-eb32-42a9-8a9b-cdfffa364842) <br/> |<span data-ttu-id="2f0c4-189">공유한 데스크톱 또는 프로그램은 다른 사람이 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-189">The desktop or program you shared is visible to the other person.</span></span>  <br/> |

 <span data-ttu-id="2f0c4-190">**회의**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-190">**Conferencing**</span></span>

|<span data-ttu-id="2f0c4-191">**작업**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-191">**Task**</span></span>|<span data-ttu-id="2f0c4-192">**예상 결과**</span><span class="sxs-lookup"><span data-stu-id="2f0c4-192">**Expected result**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2f0c4-193">Lync 모임 설정</span><span class="sxs-lookup"><span data-stu-id="2f0c4-193">Set up a Lync Meeting</span></span>](https://support.office.com/article/258f9d20-f06c-49a4-a77f-7f5ac635bb5d) <br/> |<span data-ttu-id="2f0c4-194">모임 초대는 지정한 사용자로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-194">A meeting invitation is sent to the people you specified.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-195">Lync 모임에 대한 참가자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="2f0c4-195">Change participant settings for Lync Meetings</span></span>](https://support.office.com/article/cee2aa78-d878-4a63-ad33-9c249fceced9) <br/> |<span data-ttu-id="2f0c4-196">옵션에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-196">Varies depending on the option.</span></span>  <br/> <span data-ttu-id="2f0c4-197">**팁:** Access **및 발표자에서** 로비 옵션을 무시하는 Who 설정으로 **실험할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-197">**TIP:** Under **Access and presenters**, you can experiment with different settings of the **Who will bypass the lobby** option.</span></span> <br/> |
|[<span data-ttu-id="2f0c4-198">Lync 모임 참가</span><span class="sxs-lookup"><span data-stu-id="2f0c4-198">Joining a Lync Meeting</span></span>](https://support.office.com/article/538716dc-f4f2-48c2-af96-587c62387b87) <br/> |<span data-ttu-id="2f0c4-199">대화 창이 열리면 연결되면 모임 참가자 목록에 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-199">The conversation window opens, and your name appears in the list of meeting participants once you're connected.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-200">모임 또는 통화에서 마이크 음소거 또는 음소거 비즈니스용 Skype 음소거</span><span class="sxs-lookup"><span data-stu-id="2f0c4-200">Mute or unmute your microphone in a Skype for Business meeting or call</span></span>](https://support.office.com/article/47399948-db7f-4ee5-8e61-53a94bb97704) <br/> |<span data-ttu-id="2f0c4-201">음소거 아이콘은 모임 참가자 목록의 모든 사용자 이름 옆에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-201">The Muted icon appears next to the name of everyone in the meeting participant list.</span></span> <span data-ttu-id="2f0c4-202">말할 때만 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-202">Only you can be heard when you speak.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-203">Lync PowerPoint 슬라이드 발표</span><span class="sxs-lookup"><span data-stu-id="2f0c4-203">Present PowerPoint slides in a Lync Meeting</span></span>](https://support.office.com/article/3910a2b2-01df-4b97-9451-322b598ede7e) <br/> |<span data-ttu-id="2f0c4-204">사용자 PowerPoint 프레젠테이션이 모임 단계 창의 모든 비즈니스용 Skype 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-204">Your PowerPoint presentation is displayed on everyone's computer in the Skype for Business meeting stage window.</span></span>  <br/> |
|[<span data-ttu-id="2f0c4-205">Lync 모임에서 파일 전송</span><span class="sxs-lookup"><span data-stu-id="2f0c4-205">Transfer a file in a Lync Meeting</span></span>](https://support.office.com/article/f6942910-bc1d-4a48-bf18-385778f08088) <br/> |<span data-ttu-id="2f0c4-206">업로드한 후 모임의 다른 모든 사람이 첨부 파일을 보고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0c4-206">After upload, everyone else in the meeting can view and download the attachment.</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="2f0c4-207">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2f0c4-207">Related topics</span></span>
[<span data-ttu-id="2f0c4-208">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="2f0c4-208">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="2f0c4-209">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="2f0c4-209">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


