---
title: 'Lync Server 2013: (선택 사항) 사용자에 게 전화 접속 회의 시작'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4698484c240322623760f1fd308398192bfb928f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="a5ae7-102">반드시 Lync Server 2013에서 사용자에 게 전화 접속 회의 시작</span><span class="sxs-lookup"><span data-stu-id="a5ae7-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5ae7-103">_**마지막으로 수정 된 항목:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="a5ae7-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="a5ae7-104">전화 접속 회의를 구성 하 고 테스트 하 여 제대로 작동 하는지 확인 한 후에는 사용자에 대 한 초기 개인 식별 번호 (Pin)를 설정 하 고 사용자에 게 기능의 사용 가능 여부를 알리는 것이 좋습니다 (해당 하는 경우). 초기 PIN 및 전화 접속 회의 설정 웹 페이지에 대 한 링크</span><span class="sxs-lookup"><span data-stu-id="a5ae7-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="a5ae7-105">이 단계는 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-105">This step is optional.</span></span> <span data-ttu-id="a5ae7-106">일반적으로는 **CsClientPin** cmdlet을 사용 하 여 pin을 다시 설정 하지만, 정보를 포함 하 여 환영 전자 메일을 처음으로 보낼 때이 항목의 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="a5ae7-107">전자 메일을 보내지 않으려면 대신 **Set CsClientPin** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="a5ae7-108">**Set-cspinsendcawelcomemail** 스크립트를 사용 하 여 PIN을 설정 하 고 단일 사용자에 게 환영 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="a5ae7-109">기본적으로 스크립트는 이미 설정 된 경우 PIN을 다시 설정 하지 않지만 **force** 매개 변수를 사용 하 여 pin을 강제로 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="a5ae7-110">전자 메일 메시지는 SMTP (Simple Mail Transfer Protocol)를 사용 하 여 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="a5ae7-111">**Set-cspinsendcawelcomemail** 스크립트를 반복적으로 실행 하 여 pin을 설정 하 고 사용자 그룹에 전자 메일을 보내는 스크립트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="a5ae7-112">전자 메일 템플릿 (즉, **CAWelcomeEmailTemplate** 파일)을 수정 하 여 인트라넷 페이지에 대 한 링크를 더 추가 하거나 전자 메일 텍스트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="a5ae7-113">초기 PIN을 설정 하 고 환영 전자 메일을 보내려면</span><span class="sxs-lookup"><span data-stu-id="a5ae7-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="a5ae7-114">RTCUniversalServerAdmins 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="a5ae7-115">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a5ae7-116">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-116">Run the following at the command prompt:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
        -From <email address of sender> [-Subject <subject for email message>]
        [-UserEmailAddress <destination email address>]
        [-Cc <email address of recipients who receive copy of email>]
        [-Bcc <email address of recipients who receive blind copies>]
        [-TemplatePath <path for email template>]
        [-SmtpServer] <SMTP server name>]
        [-BodyAsPlainText] [-UseSsl]
        [-Pin <new numeric PIN>] [-Force] `
        [-Credential <SMTP server credentials used to send email with the specified From address>]
    
    <span data-ttu-id="a5ae7-117">**SmtpServer**   이 스크립트는 기본적으로이 매개 변수에 **$PSEmailServer** 예약 된 환경 변수 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="a5ae7-118">**$PSEmailServer** 변수를 설정 하지 않은 경우이 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="a5ae7-119">**자격 증명**   기본적으로 스크립트는 현재 사용자의 자격 증명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="a5ae7-120">현재 사용자에 게 지정 된 보낸 사람 주소 대신 전자 메일을 보낼 수 있는 권한이 없는 경우이 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="a5ae7-121">일반적으로 전자 메일 주소를 보낸 사람 주소로 지정 하지 않는 경우이 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="a5ae7-122">예:</span><span class="sxs-lookup"><span data-stu-id="a5ae7-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="a5ae7-123">이 예에서는 새 PIN을 만든 다음 Marco에서 Bob에 게 환영 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-123">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="a5ae7-124">기본 서식 파일의 전자 메일 텍스트를 사용 하 고 HTML 형식으로 전자 메일 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="a5ae7-125">기본 제목은 "전화 접속 회의에 오신 것을 환영 합니다."입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-125">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="a5ae7-126">다른 예:</span><span class="sxs-lookup"><span data-stu-id="a5ae7-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="a5ae7-127">이 예에서는 bob에 게 기존 PIN이 있더라도 bob에 게 값이 "383042650" 인 새 PIN을 강제로 적용 한 다음 Marco에서 Bob에 게 환영 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-127">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="a5ae7-128">Credential 매개 변수를 지정 했기 때문에 명령을 실행 하는 사용자에 게 암호를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-128">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="a5ae7-129">이 전자 메일은 SSL (Secure Sockets Layer)을 사용 하 여 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5ae7-129">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

