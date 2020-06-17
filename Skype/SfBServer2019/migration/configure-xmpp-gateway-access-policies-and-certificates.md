---
title: XMPP 게이트웨이 액세스 정책 및 인증서 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP 페더레이션은 XMPP(eXtensible Messaging and Presence Protocol)에 따라 외부 배포를 정의합니다. XMPP 구성을 사용 하면 사용자가 다음을 통해 XMPP 도메인 사용자에 액세스할 수 있습니다.
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753938"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="f0afe-104">XMPP 게이트웨이 액세스 정책 및 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="f0afe-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="f0afe-105">XMPP 페더레이션은 XMPP(eXtensible Messaging and Presence Protocol)에 따라 외부 배포를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="f0afe-106">XMPP 구성을 사용 하면 사용자가 다음을 통해 XMPP 도메인 사용자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="f0afe-107">IM 및 현재 상태-사용자 에게만</span><span class="sxs-lookup"><span data-stu-id="f0afe-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="f0afe-108">비즈니스용 Skype 클라이언트에 XMPP 페더레이션 대화 상대 만들기</span><span class="sxs-lookup"><span data-stu-id="f0afe-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="f0afe-109">XMPP 페더레이션 파트너를 지원 하기 위해 정책을 구성할 때 정책은 XMPP 페더레이션 도메인의 사용자에 게 적용 되지만 SIP (session 착수 프로토콜) 서비스 공급자 또는 SIP 페더레이션 도메인의 사용자에 게는 해당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="f0afe-110">사용자가 연락처를 추가 하 고와 통신할 수 있도록 허용 하려는 각 XMPP 페더레이션 도메인에 대해 XMPP 페더레이션 파트너를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="f0afe-111">정책을 만들었으면 XMPP 게이트웨이 인증서를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f0afe-112">XMPP 기능은 비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 않지만 비즈니스용 Skype 서버 2019와 함께 사용 하는 경우 레거시 서버에서 계속 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="f0afe-113">레거시 서버 (비즈니스용 Skype 서버 2015/Lync Server 2013) XMPP 게이트웨이를 이미 배포 했으며 사용자가 레거시 XMPP 게이트웨이를 사용할 수 있도록 액세스 정책을 구성 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="f0afe-114">자세한 내용은 [XMPP 페더레이션 마이그레이션을](migrating-xmpp-federation.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0afe-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="f0afe-115">사용자가 레거시 XMPP 게이트웨이를 사용할 수 있도록 외부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f0afe-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="f0afe-116">레거시 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="f0afe-117">왼쪽 탐색 모음에서 **Federation and External Access(페더레이션 및 외부 액세스)** 를 클릭하고 **외부 액세스 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="f0afe-118">**새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="f0afe-119">외부 액세스 사용자 정책의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="f0afe-120">외부 액세스 사용자 정책에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="f0afe-121">**페더레이션 사용자와의 통신 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="f0afe-122">Select **Enable communications with XMPP federated users(XMPP 페더레이션 사용자와의 통신 사용)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="f0afe-123">**커밋**을 클릭하여 사이트 또는 사용자 정책에 대한 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f0afe-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

