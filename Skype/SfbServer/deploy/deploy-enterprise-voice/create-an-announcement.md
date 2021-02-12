---
title: 비즈니스용 Skype 서버에서 공지 만들기 또는 삭제
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 비즈니스용 Skype 서버 2016에서 공지사항 응용 프로그램에 대한 Enterprise Voice. 이는 미지정 번호에 대한 호출이 처리된 방식에 영향을 미치게 됩니다.
ms.openlocfilehash: 9f2b4fcda8e98d4b939b6b443da875dbe153546c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824908"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="1cba3-104">비즈니스용 Skype 서버에서 공지 만들기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="1cba3-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="1cba3-105">비즈니스용 Skype 서버 2016에서 공지사항 응용 프로그램에 대한 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1cba3-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="1cba3-106">이는 미지정 번호에 대한 호출이 처리된 방식에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="1cba3-107">공지 사항을 구성할 때 실제로는 미지정 번호에 대한 통화를 처리할 방법을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-107">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled.</span></span> <span data-ttu-id="1cba3-108">오디오 파일 또는 TTS(텍스트 음성 전송) 파일일 수 있는 프롬프트를 재생하거나 프롬프트를 재생하지 않고 통화를 지정된 대상으로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-108">You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="1cba3-109">미지정 번호 테이블을 정의하기 전에 공지 사항을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-109">You need to create announcements before you define the unassigned number table.</span></span> <span data-ttu-id="1cba3-110">오디오 프롬프트, TTS 프롬프트 또는 프롬프트가 없는 모든 공지에 대해 이 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-110">You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="1cba3-111">이 항목에서는 알림을 가져오고 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="1cba3-112">할당되지 않은 번호 테이블에서 알림을 할당하는 방법에 대한 자세한 내용은 [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1cba3-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="1cba3-113">미지정 번호에 대한 새 공지 만들기</span><span class="sxs-lookup"><span data-stu-id="1cba3-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="1cba3-114">새 알림을 만들려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="1cba3-115">오디오 음성 안내의 경우 자주 사용하는 오디오 녹음 응용 프로그램을 사용하여 오디오 파일을 녹음합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="1cba3-116">오디오 음성 안내의 경우 **Import-CsAnnouncementFile** cmdlet을 실행하여 오디오 파일의 내용을 파일 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="1cba3-117">**New-CsAnnouncement** cmdlet을 실행하여 알림을 만들고 알림의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="1cba3-118">오디오 음성 안내나 TTS(텍스트 음성 변환) 음성 안내를 사용하거나 또는 음성 안내를 사용하지 않고 알림을 만들려면 이 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="1cba3-119">음성 안내를 사용하지 않고 알림을 만들어야 하는 경우도 있습니다(예를 들어 메시지를 재생하지 않고 특정 대상에게 통화를 전송할 경우).</span><span class="sxs-lookup"><span data-stu-id="1cba3-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="1cba3-120">새 알림을 할당되지 않은 번호 테이블의 번호 범위에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="1cba3-121">새 알림을 만들려면</span><span class="sxs-lookup"><span data-stu-id="1cba3-121">To create a new announcement</span></span>

1. <span data-ttu-id="1cba3-122">오디오 음성 안내의 경우 오디오 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="1cba3-123">비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원 또는 위임 설치 권한에 설명된 필요한 사용자 권한으로 설치된 컴퓨터에 로그온합니다. </span><span class="sxs-lookup"><span data-stu-id="1cba3-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="1cba3-124">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1cba3-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="1cba3-125">오디오 음성 안내의 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="1cba3-126">실행:</span><span class="sxs-lookup"><span data-stu-id="1cba3-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="1cba3-p107">통화를 음성 메일로 전송하려면 SIPAddress를 sip:username@domainname;opaque=app:voicemail 형식으로 입력합니다(예: sip:bob@contoso.com;opaque=app:voicemail). 통화를 전화 번호로 전송할 경우에는 SIPAddress를 sip:number@domainname;user=phone 형식으로 입력합니다(예: sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="1cba3-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="1cba3-129">예: 오디오 음성 안내 지정</span><span class="sxs-lookup"><span data-stu-id="1cba3-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="1cba3-130">예: TTS 음성 안내 지정</span><span class="sxs-lookup"><span data-stu-id="1cba3-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="1cba3-131">이러한 cmdlet에 대한 자세한 내용과 **TextToSpeechPrompt** 매개 변수에서 사용할 언어 코드 목록을 확인하면 [New-CsAnnouncement를](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cba3-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="1cba3-132">미지정 번호에 대한 공지 삭제</span><span class="sxs-lookup"><span data-stu-id="1cba3-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="1cba3-133">공지 사항을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="1cba3-133">To delete an announcement</span></span>

1. <span data-ttu-id="1cba3-134">비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원 또는 위임 설치 권한에 설명된 필요한 사용자 권한으로 설치된 컴퓨터에 로그온합니다. </span><span class="sxs-lookup"><span data-stu-id="1cba3-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="1cba3-135">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1cba3-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="1cba3-136">조직의 모든 공지 사항을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-136">List all the announcements in your organization.</span></span> <span data-ttu-id="1cba3-137">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-137">At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="1cba3-138">결과 목록에서 삭제할 공지 사항을 찾은 다음 GUID를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-138">In the resulting list, locate the announcement you want to delete, and copy the GUID.</span></span> <span data-ttu-id="1cba3-139">그런 다음 명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1cba3-139">Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="1cba3-140">예시:</span><span class="sxs-lookup"><span data-stu-id="1cba3-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="1cba3-141">추가 옵션에 대한 자세한 내용은 [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) 및 [Remove-CsAnnouncement를 참조하세요.](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1cba3-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="1cba3-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cba3-142">See also</span></span>

[<span data-ttu-id="1cba3-143">비즈니스용 Skype 서버에서 공지 만들기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="1cba3-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="1cba3-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="1cba3-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="1cba3-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="1cba3-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="1cba3-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="1cba3-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="1cba3-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="1cba3-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

