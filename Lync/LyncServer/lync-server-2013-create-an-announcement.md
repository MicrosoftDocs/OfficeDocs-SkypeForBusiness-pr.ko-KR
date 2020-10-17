---
title: 'Lync Server 2013: 알림 만들기'
description: 'Lync Server 2013: 알림을 만듭니다.'
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
ms.openlocfilehash: cc064686ef86e04b89951fcaac7abbec28b7257c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562394"
---
# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="7ebf2-103">Lync Server 2013에서 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="7ebf2-103">Create an announcement in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ebf2-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7ebf2-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7ebf2-105">새 알림을 만들려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-105">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="7ebf2-106">오디오 음성 안내의 경우 자주 사용하는 오디오 녹음 응용 프로그램을 사용하여 오디오 파일을 녹음합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-106">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="7ebf2-107">오디오 음성 안내의 경우 **Import-CsAnnouncementFile** cmdlet을 실행하여 오디오 파일의 내용을 파일 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-107">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="7ebf2-108">**New-CsAnnouncement** cmdlet을 실행하여 알림을 만들고 알림의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-108">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="7ebf2-109">오디오 음성 안내나 TTS(텍스트 음성 변환) 음성 안내를 사용하거나 또는 음성 안내를 사용하지 않고 알림을 만들려면 이 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-109">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7ebf2-110">음성 안내를 사용하지 않고 알림을 만들어야 하는 경우도 있습니다(예를 들어 메시지를 재생하지 않고 특정 대상에게 통화를 전송할 경우).</span><span class="sxs-lookup"><span data-stu-id="7ebf2-110">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="7ebf2-111">새 알림을 할당되지 않은 번호 테이블의 번호 범위에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-111">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="7ebf2-112">이 항목에서는 알림을 가져오고 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-112">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="7ebf2-113">지정 되지 않은 번호 테이블에 공지를 할당 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 지정 되지 않은 번호 테이블 구성을](lync-server-2013-configure-the-unassigned-number-table.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-113">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="7ebf2-114">새 알림을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7ebf2-114">To create a new announcement</span></span>

1.  <span data-ttu-id="7ebf2-115">오디오 음성 안내의 경우 오디오 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-115">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="7ebf2-116">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-116">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="7ebf2-117">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="7ebf2-118">오디오 음성 안내의 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-118">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="7ebf2-119">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-119">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="7ebf2-p103">통화를 음성 메일로 전송하려면 SIPAddress를 sip:username@domainname;opaque=app:voicemail 형식으로 입력합니다(예: sip:bob@contoso.com;opaque=app:voicemail). 통화를 전화 번호로 전송할 경우에는 SIPAddress를 sip:number@domainname;user=phone 형식으로 입력합니다(예: sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="7ebf2-p103">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="7ebf2-122">예: 오디오 음성 안내 지정</span><span class="sxs-lookup"><span data-stu-id="7ebf2-122">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="7ebf2-123">예: TTS 음성 안내 지정</span><span class="sxs-lookup"><span data-stu-id="7ebf2-123">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="7ebf2-124">이러한 cmdlet에 대 한 자세한 내용을 보고, **TextToSpeechPrompt** 매개 변수에 사용할 언어 코드의 목록을 보려면 [New csannouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ebf2-124">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ebf2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ebf2-125">See Also</span></span>


[<span data-ttu-id="7ebf2-126">경우 import-csannouncementfile</span><span class="sxs-lookup"><span data-stu-id="7ebf2-126">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="7ebf2-127">새 CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="7ebf2-127">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="7ebf2-128">Lync Server 2013에서 지정 되지 않은 번호 테이블 구성</span><span class="sxs-lookup"><span data-stu-id="7ebf2-128">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

