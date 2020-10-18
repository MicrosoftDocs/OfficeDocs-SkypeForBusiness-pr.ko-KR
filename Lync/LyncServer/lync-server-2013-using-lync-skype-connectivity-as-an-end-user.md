---
title: 'Lync Server 2013: 최종 사용자로 Lync-Skype 연결 사용'
description: 'Lync Server 2013: 최종 사용자로 Lync-Skype 연결을 사용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd669a5cf0b15f7fb2d411e4456553f5469d9f96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580384"
---
# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="d76c1-103">최종 사용자로 Lync Server 2013에서 Lync-Skype 연결 사용</span><span class="sxs-lookup"><span data-stu-id="d76c1-103">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d76c1-104">_**마지막으로 수정 된 항목:** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="d76c1-104">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="d76c1-105">Lync-Skype 연결을 사용 하면 Skype 사용자와 Lync 사용자가 서로를 연락처로 추가 하 고, exchange 인스턴트 메시지를 보내고, 음성 및 화상 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-105">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="d76c1-106">Skype 사용자가 Lync 사용자를 추가할 때 Skype 사용자는 Lync 사용자의 SIP (session 시작 프로토콜)가 포함 된 Skype에서 연락처를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-106">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="d76c1-107">반대로 lync 사용자가 Skype 대화 상대를 추가할 때 lync 사용자는 Lync에서 skype 사용자 이름이 아닌 Skype 사용자의 Microsoft 계정 (MSA)을 포함 하는 연락처를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-107">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="d76c1-108">**MSA 란?**</span><span class="sxs-lookup"><span data-stu-id="d76c1-108">**What is an MSA?**</span></span> <span data-ttu-id="d76c1-109">Lync 대화 상대와 통신 하려면 skype 사용자가 Microsoft 계정 (이전의 Windows Live ID)을 사용 하 여 Skype에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-109">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="d76c1-110">Microsoft 계정은 전자 메일 주소와 암호의 조합으로 구성 되며, Microsoft OneDrive 저장 기술, Windows Phone, Microsoft Xbox LIVE online 게임 서비스, Microsoft Outlook messaging 및 공동 작업 클라이언트 (및 이전 버전에서는 Microsoft Hotmail 웹 기반 전자 메일 서비스 또는 Windows Live Messenger)와 같은 서비스에 로그인 하는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-110"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="d76c1-111">전자 메일 주소와 암호를 사용 하 여 이러한 서비스나 다른 서비스에 로그인 하는 경우 이미 Microsoft 계정이 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-111"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="d76c1-112">Microsoft 계정을 만드는 방법에 대 한 자세한 내용은의 Microsoft 계정 등록 페이지를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061) .</span><span class="sxs-lookup"><span data-stu-id="d76c1-112"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="d76c1-113">다양 한 응용 프로그램 및 서비스에서 사용자의 single sign-on을 사용 하 여 기존 Skype 계정을 Microsoft 계정에 병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-113">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="d76c1-114">계정이 병합 되 면 Skype 사용자는 Lync 사용자에 게 연락처 요청을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-114">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d76c1-115">Lync 및 Skype 사용자가 서로 완전히 통신할 수 있도록 하려면 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-115">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d76c1-116">Skype 사용자는 Microsoft 계정 (MSA)을 사용 하 여 Skype 클라이언트에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-116">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="d76c1-117">Lync 관리자가 공용 IM 연결을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-117">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="d76c1-118">Skype 사용자가 Lync 대화 상대를 추가할 때 Lync 연락처가 연락처 이름 아래에 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-118">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="d76c1-119">이는 Lync URI를 찾은 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-119">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="d76c1-120">Skype 사용자가 Lync 대화 상대를 추가 하 고 해당 Lync 도메인에 대해 0 개의 검색 결과가 반환 되 면 PIC 프로 비전 프로세스가 완료 되지 않았거나 Lync 도메인이 아직 설정 되지 않은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-120">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="d76c1-121">Lync 및 Skype 사용자, IM, 비디오 및 현재 상태에 대 한 개인 정보 설정에 따라 각 사용자가 새 연락처를 수락 하지 않으면 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-121">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d76c1-122">**Lync 2013에 Skype 연락처를 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="d76c1-122">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="d76c1-123">Lync에서 **대화 상대 추가를 클릭 하 고 조직에 없는 대화 상대를 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-123">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="d76c1-124">사용 가능한 대화 상대 공급자 목록에서 **Skype**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-124">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="d76c1-125">**메신저 주소** 필드에 Skype 사용자의 Microsoft 계정 (MSA)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-125">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="d76c1-126">**대화 상대 그룹에 추가** 드롭다운 상자에서 사용자를 추가할 대화 상대 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-126">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="d76c1-127">**개인 정보 취급 방침 설정** 드롭다운 상자에서 해당 하는 대화 상대 설정을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-127">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="d76c1-128">사용자는 이제 Lync에서 연락처로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-128">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="d76c1-129">사용자를 선택 하 고 사용자 이름을 마우스 오른쪽 단추로 클릭 한 다음 **대화 상대 카드** 보기를 클릭 하 여 사용자 속성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-129">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="d76c1-130">이제 새로 추가한 Skype 사용자와의 음성 또는 비디오 통화를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-130">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="d76c1-131">연락처 지원에 대 한 자세한 내용은 [Lync에서 연락처 추가](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d76c1-131">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="d76c1-132">Skype 사용자의 Microsoft 계정에서 <strong>bob@contoso.com</strong> 과 같은 사용자 지정 도메인 이름을 사용 하는 경우 lync 사용자는 다음 두 가지 방법으로 lync에 해당 microsoft 계정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-132">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="d76c1-133">**대화 상대 추가** 아이콘 사용</span><span class="sxs-lookup"><span data-stu-id="d76c1-133">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="d76c1-134">**사람 찾기 또는 채팅방을 사용 하거나 전화 걸기 번호** 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-134">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="d76c1-135">각 인스턴스에서 Lync 사용자는 <strong>사용자 (도메인 이름) @msn</strong> 와 같은 형식으로 Skype 사용자의 전자 메일을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-135">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d76c1-136">다음 도메인 이름을 사용 하는 Microsoft 계정에는이 단계가 필요 하지 않습니다 ( <STRONG>@live .com, @hotmail .com 또는 @outlook .com</STRONG>).</span><span class="sxs-lookup"><span data-stu-id="d76c1-136">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="d76c1-137">지원 되는 사용자 지정 도메인 이름에 대 한 자세한 내용은 <A href="https://support.microsoft.com/kb/897567">지원 되는 공용 IM 도메인</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d76c1-137">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="d76c1-138">**사용자 지정 도메인 이름을 사용할 때 Lync에 Skype 연락처를 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="d76c1-138">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="d76c1-139">Lync에서 **대화 상대 추가를 클릭 하 고 조직에 없는 대화 상대를 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-139">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="d76c1-140">사용 가능한 대화 상대 공급자 목록에서 **Skype**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-140">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="d76c1-141">**IM 주소** 필드에 <strong>사용자 (도메인 이름) @msn</strong>형식으로 Skype 사용자의 Microsoft 계정 (MSA)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-141">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="d76c1-142">따라서 사용자 bob@contoso.com에 대 한 항목은 <strong> bob (contoso) @msn 됩니다. <strong></span><span class="sxs-lookup"><span data-stu-id="d76c1-142">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="d76c1-143">**대화 상대 그룹에 추가** 드롭다운 목록 상자에서 사용자를 추가할 대화 상대 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-143">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="d76c1-144">**개인 정보 취급 방침 설정** 드롭다운 목록 상자에서 적절 한 연락처 설정을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-144">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="d76c1-145">Lync 사용자는 **다른 사람 찾기 또는 채팅방** 을 사용 하거나 lync에서 번호 필드에 전화를 걸 수 있으며, 다음 <strong>사용자 (도메인 이름) @msn</strong> 와 비슷한 주소를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-145">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="d76c1-146">따라서 bob@contoso.com Microsoft 계정에 대 한 항목은 <strong>bob (contoso) @msn 합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="d76c1-146">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="d76c1-147">연락처 그룹에 연락처를 추가 하 고 해당 하는 개인 정보 취급 방침을 선택 하려면이 절차의 4 단계와 5 번을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-147">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="d76c1-148">**Lync 연락처를 Skype에 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="d76c1-148">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="d76c1-149">Skype에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-149">Sign in to Skype.</span></span> <span data-ttu-id="d76c1-150">Skype 사용자는 Microsoft 계정 (MSA)을 사용 하 여 Skype 클라이언트에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-150">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="d76c1-151">연락처 추가 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-151">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="d76c1-152">Lync 사용자의 SIP URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-152">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="d76c1-153">예: bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d76c1-153">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="d76c1-154">Skype가 검색 결과에서 일치 하는 항목을 찾은 경우 Lync 사용자 이름 아래에 있는 **lync** 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-154">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="d76c1-155">이는 Lync 클라이언트의 SIP URI가 성공한 Skype 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-155">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="d76c1-156">이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-156">Click the name.</span></span>

5.  <span data-ttu-id="d76c1-157">창의 오른쪽 위 모서리에서 연락처에 추가를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-157">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="d76c1-158">이제 새 연락처가 대화 상대 목록에 추가 되지만 요청을 수락 하기 전 까지는 해당 상태 아이콘 대신 물음표가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-158">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="d76c1-159">새 연락처가 요청을 수락 하면 온라인 상태인 경우를 확인 하 고, IM 대화를 시작 하 고, 오디오 및 비디오 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-159">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d76c1-160">Lync Server 관리자는 들어오는 요청을 허용 하도록 Lync 사용자의 정책 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-160">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="d76c1-161">그렇지 않으면 Lync 사용자가 Skype 사용자 로부터 대화 상대 요청을 수신 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-161">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="d76c1-162">Lync 사용자 정책 설정의 구성에 따라 Lync 클라이언트의 <STRONG>새</STRONG> 탭에 Skype 사용자 추가 요청이 표시 됩니다. Skype 사용자와의 통신을 시작 하려면 Lync 사용자가 즐겨찾기 목록 또는 대화 상대 목록에 Skype 사용자를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-162">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="d76c1-163">아래 이미지에는 Lync 클라이언트의 <STRONG>새</STRONG> 탭 위치가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-163">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="d76c1-164">Lync 사용자는 lync 알림을 구성 하 여 Skype 사용자가 보낸 요청이 나타나고 Lync 사용자가 검색할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-164">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="d76c1-165">Lync 알림을 구성 하려면 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-165">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="d76c1-166">**Lync 알림을 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="d76c1-166">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="d76c1-167">Lync 클라이언트에서 **옵션** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-167">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="d76c1-168">**경고**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-168">Select **Alerts**.</span></span>

3.  <span data-ttu-id="d76c1-169">**일반 경고**에서 **다른 사용자가 자신의 대화 상대 목록에 나를 추가할 때**알림을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-169">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="d76c1-170">**Lync를 사용 하지 않는 연락처**에서 초대 허용을 선택 하 고 **다른 모든 통신을 차단**합니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-170">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="d76c1-171">**확인** 을 클릭 하 여 옵션 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d76c1-171">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

