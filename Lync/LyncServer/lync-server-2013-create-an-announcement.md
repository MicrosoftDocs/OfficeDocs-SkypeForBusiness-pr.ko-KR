---
title: 'Lync Server 2013: 알림 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfae1817cb47c769885ca42a7ca3ff6f57f7b669
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="95670-102">Lync Server 2013에서 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="95670-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95670-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="95670-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="95670-104">새 알림을 만들려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="95670-105">오디오 메시지가 표시 되는 경우 좋아하는 오디오 녹음 응용 프로그램을 사용 하 여 오디오 파일을 녹음 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="95670-106">오디오 프롬프트의 경우 **CsAnnouncementFile** cmdlet을 실행 하 여 오디오 파일의 콘텐츠를 파일 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95670-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="95670-107">**새 csannouncement** cmdlet을 실행 하 여 알림을 만들고 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95670-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="95670-108">오디오 프롬프트, 텍스트 음성 변환 (TTS) 프롬프트 또는 메시지가 표시 되지 않는 알림을 만들려면이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="95670-109">메시지를 재생 하지 않고 특정 대상에 전화를 거는 등의 메시지가 표시 되지 않은 상태에서 알림을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95670-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="95670-110">지정 하지 않은 번호 표의 번호 범위에 새 공지 사항을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="95670-111">이 항목에서는 알림을 가져오고 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="95670-112">할당 되지 않은 번호 표에 공지 사항을 할당 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 지정 하지 않은 번호 표 구성을](lync-server-2013-configure-the-unassigned-number-table.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95670-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="95670-113">새 알림을 만들려면</span><span class="sxs-lookup"><span data-stu-id="95670-113">To create a new announcement</span></span>

1.  <span data-ttu-id="95670-114">오디오 메시지가 표시 되는 경우 오디오 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95670-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="95670-115">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="95670-116">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="95670-117">오디오 프롬프트에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="95670-118">런</span><span class="sxs-lookup"><span data-stu-id="95670-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="95670-119">음성 메일로 통화를 전송 하는 경우 sip: username@domainname, 불투명 = 앱: 음성 메일 (예: sip: bob@contoso, 불투명 = app) 형식으로 SIPAddress를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-119">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="95670-120">전화 번호로 통화를 전송 하는 경우 sip: number@domainname, user = phone 형식으로 SIPAddress를 입력 합니다 (예: sip: + 14255550121@contoso 사용자 = 휴대폰).</span><span class="sxs-lookup"><span data-stu-id="95670-120">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="95670-121">예를 들어 오디오 프롬프트를 지정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="95670-122">예를 들어 TTS 프롬프트를 지정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="95670-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="95670-123">이러한 cmdlet에 대 한 자세한 내용 및 **TextToSpeechPrompt** 매개 변수에 사용할 언어 코드 목록을 보려면 [새 csannouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95670-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95670-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95670-124">See Also</span></span>


[<span data-ttu-id="95670-125">가져오기-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="95670-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="95670-126">새 CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="95670-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="95670-127">Lync Server 2013에서 지정되지 않은 번호 테이블 구성</span><span class="sxs-lookup"><span data-stu-id="95670-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

