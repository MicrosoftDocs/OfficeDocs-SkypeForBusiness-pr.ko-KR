---
title: 'Lync Server 2013: 호스팅된 SIP 페더레이션 공급자 만들기 또는 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6c97255ce1dc9fce00d9eca6f358f4c68e1ff8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="71422-102">Lync Server 2013에서 호스팅된 SIP 페더레이션 공급자 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="71422-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71422-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="71422-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="71422-104">호스트 된 공급자 IM (인스턴트 메시징) 연결을 사용 하면 조직의 사용자가 Microsoft Office 365 및 Lync Online을 포함 하 여 호스팅된 공급자가 제공 하는 IM 서비스 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71422-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including the Microsoft Office 365 and Lync Online.</span></span>

<span data-ttu-id="71422-105">각 호스팅된 공급자는 공급자의 Edge 서버 정규화 된 도메인 이름으로 구성 되며, 기본 확인 수준을 **통해 사용자는이 공급자를 사용 하는 대화 상대 목록에 있는 사용자와만 통신할 수**있습니다.</span><span class="sxs-lookup"><span data-stu-id="71422-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="71422-106">호스트 된 공급자를 만들거나 편집 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="71422-107">호스팅된 공급자를 만들거나 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="71422-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="71422-108">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="71422-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="71422-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="71422-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="71422-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="71422-111">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **SIP 페더레이션된 공급자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="71422-112">호스트 된 새 공급자를 만들어야 하는 경우 **새로 만들기** 를 클릭 한 다음 **호스팅된 공급자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="71422-113">호스트 된 공급자 목록에서 항목을 편집 해야 하는 경우에는 호스팅 공급자를 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="71422-114">**SIP 페더레이션 공급자 편집** 페이지에서 다음 설정을 입력 하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71422-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="71422-115">**이 공급자**   와 통신 사용이 설정을 선택 하면이 공급자의 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71422-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="71422-116">**공급자 이름:**   필요한 속성에는 공급자 이름을 SIP 페더레이션된 공급자 목록에 반영할 형식으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="71422-117">**FQDN (액세스에 지 서비스):**   필수 속성인 경우 구성 중인 호스트 된 공급자의 액세스에 지 서비스에 대 한 정규화 된 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="71422-118">이 정보는 호스팅된 공급자가 제공 해야 하며 호스팅된 공급자가 호스트 된 공급자에 대 한 액세스 경계 서비스의 FQDN을 변경 하는 경우에만 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="71422-119">**기본 확인 수준:**    **이 공급자를 사용 하는 사용자가 대화 상대 목록에 있는 사용자와 통신할 수 있도록 허용** 하는 기본 설정은 수락 하 고 연락처 목록에 있는 연락처와의 통신을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="71422-120">**사용자가이 공급자를 사용 하는 모든 사용자와 통신 하도록 허용을** 선택 하면 연락처 초대를 받아서 수락 해야 하는 제한이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71422-120">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="71422-121">이 설정은 호스팅된 공급자의 네트워크에서 사용자에 게 연락할 수 있는 사용자를 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71422-121">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="71422-122">설정 구성을 완료 했으면 **커밋을** 클릭 하 여 저장 하거나 **취소** 를 클릭 하 여 변경 내용을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="71422-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71422-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71422-123">See Also</span></span>


[<span data-ttu-id="71422-124">Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="71422-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="71422-125">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="71422-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

