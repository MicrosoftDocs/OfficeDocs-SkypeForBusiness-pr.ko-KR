---
title: 'Lync Server 2013: 새 PIN 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new PIN policy
ms:assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182547(v=OCS.15)
ms:contentKeyID: 48184777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fec255badd1c48b724b792e55f2b9db39cdc9784
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-pin-policy-in-lync-server-2013"></a><span data-ttu-id="cebe3-102">Lync Server 2013에서 새 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="cebe3-102">Create a new PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cebe3-103">_**마지막으로 수정 된 항목:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="cebe3-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="cebe3-104">**Pin 정책** 페이지를 사용 하 여 IP 전화와 함께 Lync 2013에 연결 하는 사용자에 게 pin (개인 식별 번호) 인증을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-104">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="cebe3-105">PIN 인증을 사용하려면 웹 서비스 설정에서 **PIN 인증 사용**이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="cebe3-106">자세한 내용은 [Modify 기존 웹 서비스 구성 설정에서 Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cebe3-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="cebe3-107">사용자 수준 또는 사이트 수준 PIN 정책을 만들려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="cebe3-108">사용자 또는 사이트 PIN 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="cebe3-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="cebe3-109">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="cebe3-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cebe3-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cebe3-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cebe3-112">왼쪽 탐색 모음에서 **보안**을 클릭하고 **PIN 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="cebe3-113">**PIN 정책** 페이지에서 **새로 만들기**를 클릭한 다음, 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-113">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="cebe3-p103">사용자 수준 정책을 만들려면 **사용자 정책**을 클릭합니다. **새 PIN 정책**의 **이름**에 정책에 대해 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="cebe3-p104">사이트 수준 정책을 만들려면 **사이트 정책**을 클릭합니다. **사이트 선택** 검색 필드에 정책을 만들 사이트의 이름 전부 또는 일부를 입력합니다. 사이트 결과 목록에서 원하는 사이트를 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="cebe3-119">**설명** 필드에 PIN 정책에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-119">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="cebe3-p105">**최소 PIN 길이** 필드에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="cebe3-p106">사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="cebe3-125">**최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수**에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-125">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="cebe3-p107">PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="cebe3-129">**PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-129">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="cebe3-p108">**PIN 기록 카운트**에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="cebe3-p109">PIN에서 연속하는 숫자, 반복되는 숫자 집합 등의 공통 숫자 패턴을 허용하려면 **공통 패턴 허용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다. 기본적으로는 복잡한 숫자 패턴만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cebe3-135">공통 패턴은 허용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-135">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="cebe3-136">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cebe3-136">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

