---
title: 비즈니스용 Skype 서버에서 공지 사항 만들기 또는 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대 한 공지 사항을 만들거나 삭제 합니다. 이는 할당 되지 않은 번호로의 호출이 처리 되는 방식에 영향을 줍니다.
ms.openlocfilehash: 6160631473a2ead839346e53f9f63294a7959289
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191352"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="f6d77-104">비즈니스용 Skype 서버에서 공지 사항 만들기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="f6d77-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="f6d77-105">비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대 한 공지 사항을 만들거나 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="f6d77-106">이는 할당 되지 않은 번호로의 호출이 처리 되는 방식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="f6d77-107">알림을 구성 하는 경우에는 할당 되지 않은 번호로 전화를 처리 하는 방법을 실제로 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-107">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled.</span></span> <span data-ttu-id="f6d77-108">오디오 파일이 나 텍스트 음성 변환 (TTS) 파일이 될 수 있는 프롬프트를 재생 하거나, 프롬프트를 재생 하지 않고 지정 된 대상으로 통화를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-108">You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="f6d77-109">할당 되지 않은 번호 표를 정의 하기 전에 공지 사항을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-109">You need to create announcements before you define the unassigned number table.</span></span> <span data-ttu-id="f6d77-110">오디오 프롬프트, TTS 프롬프트 또는 메시지 표시 안 함을 사용 하는 모든 공지 사항에 대해이 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-110">You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="f6d77-111">이 항목에서는 알림을 가져오고 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="f6d77-112">지정 되지 않은 번호 테이블에 공지 사항을 할당 하는 방법에 대 한 자세한 내용은 지정 하지 [않은 번호 표 구성을](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6d77-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="f6d77-113">할당 되지 않은 번호에 대 한 새 공지 사항 만들기</span><span class="sxs-lookup"><span data-stu-id="f6d77-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="f6d77-114">새 알림을 만들려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="f6d77-115">오디오 메시지가 표시 되는 경우 좋아하는 오디오 녹음 응용 프로그램을 사용 하 여 오디오 파일을 녹음 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="f6d77-116">오디오 프롬프트의 경우 **CsAnnouncementFile** cmdlet을 실행 하 여 오디오 파일의 콘텐츠를 파일 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="f6d77-117">**새 csannouncement** cmdlet을 실행 하 여 알림을 만들고 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="f6d77-118">오디오 프롬프트, 텍스트 음성 변환 (TTS) 프롬프트 또는 메시지가 표시 되지 않는 알림을 만들려면이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="f6d77-119">메시지를 재생 하지 않고 특정 대상에 전화를 거는 등의 메시지가 표시 되지 않은 상태에서 알림을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="f6d77-120">지정 하지 않은 번호 표의 번호 범위에 새 공지 사항을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="f6d77-121">새 알림을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f6d77-121">To create a new announcement</span></span>

1. <span data-ttu-id="f6d77-122">오디오 메시지가 표시 되는 경우 오디오 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="f6d77-123">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="f6d77-124">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="f6d77-125">오디오 프롬프트에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-125">For audio prompts, run:</span></span>

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="f6d77-126">런</span><span class="sxs-lookup"><span data-stu-id="f6d77-126">Run:</span></span>

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="f6d77-127">음성 메일로 통화를 전송 하는 경우 sip: username @ domainname, 불투명 = 앱: 보이스 메일 형식 (예: sip: bob@contoso.com, 불투명 = 앱-음성 메일) 형식의 SIPAddress를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-127">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="f6d77-128">전화 번호로 통화를 전송 하는 경우 sip: number @ domainname, user = phone 형식으로 SIPAddress를 입력 합니다 (예를 들어 sip: + 14255550121@contoso.com, user = phone).</span><span class="sxs-lookup"><span data-stu-id="f6d77-128">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="f6d77-129">예를 들어 오디오 프롬프트를 지정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-129">For example, to specify an audio prompt:</span></span>

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="f6d77-130">예를 들어 TTS 프롬프트를 지정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-130">For example, to specify a TTS prompt:</span></span>

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="f6d77-131">이러한 cmdlet에 대 한 자세한 내용 및 **TextToSpeechPrompt** 매개 변수에 사용할 언어 코드 목록을 보려면 [새 csannouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6d77-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="f6d77-132">할당 되지 않은 번호에 대 한 공지 사항 삭제</span><span class="sxs-lookup"><span data-stu-id="f6d77-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="f6d77-133">공지 사항을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="f6d77-133">To delete an announcement</span></span>

1. <span data-ttu-id="f6d77-134">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="f6d77-135">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="f6d77-136">조직의 모든 공지 사항을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-136">List all the announcements in your organization.</span></span> <span data-ttu-id="f6d77-137">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-137">At the command line, run:</span></span>

   ```
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="f6d77-138">결과 목록에서 삭제 하려는 공지 사항을 찾아 GUID를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-138">In the resulting list, locate the announcement you want to delete, and copy the GUID.</span></span> <span data-ttu-id="f6d77-139">그런 다음 명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-139">Then, at the command line, run:</span></span>

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="f6d77-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d77-140">For example:</span></span>

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="f6d77-141">추가 옵션에 대 한 자세한 내용은 [Csannouncement 가져오기](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) 및 [-csannouncement 제거](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6d77-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6d77-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6d77-142">See also</span></span>

[<span data-ttu-id="f6d77-143">비즈니스용 Skype 서버에서 공지 사항 만들기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="f6d77-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="f6d77-144">가져오기-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="f6d77-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="f6d77-145">새 CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="f6d77-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="f6d77-146">CsAnnouncement 제거</span><span class="sxs-lookup"><span data-stu-id="f6d77-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="f6d77-147">다운로드-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="f6d77-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

