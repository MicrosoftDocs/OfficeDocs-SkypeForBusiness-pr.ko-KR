---
title: XMPP 게이트웨이 액세스 정책 및 인증서 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 022d396d9d87b0112a24d06ee6a863f98795dec8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40982368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="4f5ff-102">XMPP 게이트웨이 액세스 정책 및 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="4f5ff-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f5ff-103">_**마지막으로 수정한 주제:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="4f5ff-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="4f5ff-104">XMPP federation는 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜)를 기반으로 외부 배포를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="4f5ff-105">XMPP 구성은 다음을 수행 하 여 Lync 사용자가 XMPP 도메인 사용자에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="4f5ff-106">IM 및 현재 상태 – 사용자에만 해당</span><span class="sxs-lookup"><span data-stu-id="4f5ff-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="4f5ff-107">Lync 클라이언트에서 XMPP 페더레이션 대화 만들기</span><span class="sxs-lookup"><span data-stu-id="4f5ff-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="4f5ff-108">XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션 파트너 지원에 대 한 정책을 구성할 때 정책은 XMPP 페더레이션 도메인의 사용자에 게 적용 되지만 SIP (세션 초기화 프로토콜) 서비스 공급자의 사용자에 게는 적용 되지 않습니다. (예: Windows Live) 또는 SIP 페더레이션 도메인</span><span class="sxs-lookup"><span data-stu-id="4f5ff-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="4f5ff-109">사용자가 연락처를 추가 하 고 통신 하는 데 사용할 각 XMPP 페더레이션 도메인에 대해 XMPP 페더레이션 파트너를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="4f5ff-110">정책이 설정 되 면 XMPP 게이트웨이 인증서를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f5ff-111">XMPP 게이트웨이 마이그레이션을 시작 하려면 Lync Server 2013 XMPP 게이트웨이를 배포 하 고 Lync Server 2013 XMPP 게이트웨이에 대 한 사용자를 사용 하도록 설정 하는 액세스 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="4f5ff-112">이 단계를 수행 하기 전에 모든 사용자가 Lync Server 2013 배포로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="4f5ff-113">자세한 내용은 <A href="configure-xmpp-gateway-on-lync-server-2013.md">Lync Server 2013에서 XMPP 게이트웨이 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="4f5ff-114">Lync Server 2013 XMPP Gateway에 대 한 사용자를 사용할 수 있도록 외부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="4f5ff-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="4f5ff-115">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="4f5ff-116">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="4f5ff-117">**새로 만들기** 를 클릭 한 다음 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="4f5ff-118">외부 액세스 사용자 정책의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="4f5ff-119">외부 액세스 사용자 정책에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="4f5ff-120">**페더레이션 사용자와의 통신 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="4f5ff-121">**XMPP 페더레이션 사용자와 통신 사용을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="4f5ff-122">**커밋을** 클릭 하 여 사이트 또는 사용자 정책의 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f5ff-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

