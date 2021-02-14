---
title: 조직의 SIP 페더레이션 제공자 관리
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: SIP 페더타이트 공급자 사용자에 대한 지원을 구성하는 방법을 자세히 알아보고,
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823568"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="7e2fe-103">비즈니스용 Skype 서버에서 조직에 대한 SIP 페더타 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="7e2fe-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="7e2fe-104">SIP 페더레이션 공급자의 사용자를 지원하도록 구성하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="7e2fe-105">SIP 페더레이션 공급자 대화 상대와 통신할 수 있도록 지원하려면 하나 이상의 외부 사용자 액세스 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="7e2fe-106">지원할 호스팅된 공급자를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="7e2fe-107">지원할 공용 메신저 공급자를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="7e2fe-108">비즈니스용 Skype 서버에서 공용 SIP 페더리 공급자 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="7e2fe-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="7e2fe-109">공용 IM(인스턴트 메시징) 연결을 사용하면 조직의 사용자가 IM을 사용하여 공용 공급자가 제공하는 IM 서비스 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="7e2fe-110">비즈니스용 Skype 서버에는 인스턴트 메시징에 대한 공용 공급자 구성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="7e2fe-111">각 공용 공급자는 공급자의 에지 서버 정규화된 도메인 이름과 기본 확인 수준인 **이 공급자를 사용하는 연락처 목록의 사용자와만 통신할 수 있도록 허용** 으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="7e2fe-112">기본 설정에서는 어떠한 공용 공급자도 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="7e2fe-113">공용 공급자를 사용하도록 설정하기 전에 사용권 계약 및 프로비전 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="7e2fe-114">라이선스 설정 및 프로비전 작업을 완료하기 전에도 해당 공급자를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="7e2fe-115">하지만 필수 구성 요소 작업을 완료하기 전까지는 사용자가 해당 공급자의 연락처와 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="7e2fe-116">공용 공급자의 라이선스 및 프로비전에 대한 자세한 내용은 공용 사용자 액세스 제어를 위한 정책 [구성을 참조합니다.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="7e2fe-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="7e2fe-117">다음 절차에 따라 공용 공급자를 만들거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="7e2fe-118">공용 공급자를 만들거나 편집하려면</span><span class="sxs-lookup"><span data-stu-id="7e2fe-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="7e2fe-119">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7e2fe-120">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7e2fe-121">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스** 를 클릭한 다음 **SIP 페더레이션 공급자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="7e2fe-122">새 공용 공급자를 만들려면 **새로 만들기** 를 클릭하고 **공용 공급자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="7e2fe-123">공용 공급자 목록에서 항목을 편집해야 하는 경우 해당 공용 공급자를 선택하고 **편집** 을 클릭한 후 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="7e2fe-124">**SIP 페더레이션 공급자 편집** 페이지에서는 다음 설정을 입력하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="7e2fe-125">**이 공급자와의 통신 사용**   이 설정을 선택하면 이 공급자의 사용자와 IM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="7e2fe-126">**공급자 이름:**    SIP 페더레이션 공급자 목록에 반영할 공급자의 이름을 입력합니다(필수 속성).</span><span class="sxs-lookup"><span data-stu-id="7e2fe-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="7e2fe-127">**FQDN(액세스 에지 서비스):**   필수 속성으로 구성할 공급자의 액세스 에지 서비스의 정식 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="7e2fe-128">이 정보는 기본 항목으로 제공되며, 공용 공급자가 액세스 에지 서비스의 FQDN을 바꿀 경우에만 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="7e2fe-129">**기본 확인 수준:**    기본 설정인 **이 공급자를 사용하는 연락처 목록의 사용자와 통신할 수 있도록 허용** 을 선택하면 사용자가 수락했고 사용자의 연락처 목록에 있는 연락처로 통신이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="7e2fe-p104">**이 공급자를 사용하는 모든 사람과 통신할 수 있도록 허용** 을 선택하면 연락처 초대를 수신하고 허용해야 하는 제한 사항이 제거됩니다. 이 설정은 공용 공급자의 네트워크에서 사용자에게 연락할 수 있는 사람을 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-p104">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="7e2fe-132">설정 구성을 마쳤으면 **커밋** 을 클릭해서 저장하거나 **취소** 를 클릭해서 변경 내용을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="7e2fe-133">비즈니스용 Skype 서버에서 호스팅된 SIP 페더리 공급자 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="7e2fe-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="7e2fe-134">호스트된 공급자 IM(인스턴트 메시징) 연결을 사용하면 조직의 사용자가 IM을 사용하여 호스팅된 공급자가 제공하는 IM 서비스 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="7e2fe-135">각 호스트된 공급자는 공급자의 에지 서버 정규화된 도메인 이름 및 기본 확인 수준 **대화 상대 목록에서 이 공급자를 사용하는 사용자와의 통신만 허용** 을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="7e2fe-136">다음 절차에 따라 호스팅된 공급자를 만들거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="7e2fe-137">호스트된 공급자를 만들거나 편집하려면</span><span class="sxs-lookup"><span data-stu-id="7e2fe-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="7e2fe-138">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7e2fe-139">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7e2fe-140">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스** 를 클릭한 다음 **SIP 페더레이션 공급자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="7e2fe-141">새 호스트된 공급자를 만들어야 하는 경우 **새로 만들기** 를 클릭하고 **호스트된 공급자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="7e2fe-142">호스트된 공급자 목록의 항목을 편집해야 하는 경우 호스트된 공급자를 선택하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="7e2fe-143">**SIP 페더레이션 공급자 편집** 페이지에서는 다음 설정을 입력하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="7e2fe-144">**이 공급자와의 통신 사용:**    이 설정을 선택하면 해당 공급자의 사용자와 통신을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="7e2fe-145">**공급자 이름:**    SIP 페더레이션 공급자 목록에 반영할 공급자의 이름을 입력합니다(필수 속성).</span><span class="sxs-lookup"><span data-stu-id="7e2fe-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="7e2fe-146">**FQDN(액세스 에지 서비스):**   필수 속성을 구성할 호스팅된 공급자의 액세스 에지 서비스의 정식 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="7e2fe-147">이 정보는 호스팅된 공급자가 제공해야 하며, 호스팅된 공급자가 호스팅된 공급자의 액세스 에지 서비스의 FQDN을 변경하는 경우만 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="7e2fe-148">**기본 확인 수준:**    기본 설정인 **대화 상대 목록에서 이 공급자를 사용하는 사용자와의 통신만 허용** 을 선택하면 통신을 수락하여 대화 상대 목록에 있는 대화 상대와의 통신만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="7e2fe-p106">**이 공급자를 사용하는 모든 사용자와의 통신 허용** 을 선택하면 대화 상대 초대를 받아 수락할 때 적용된 제한이 제거됩니다. 이 설정은 호스트된 공급자 네트워크에서 사용자와 대화를 할 수 있는 사람을 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-p106">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="7e2fe-151">설정을 모두 구성한 후에 **커밋** 을 클릭하여 변경 내용을 저장하거나 **취소** 를 클릭하여 변경을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2fe-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="7e2fe-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e2fe-152">See Also</span></span>


[<span data-ttu-id="7e2fe-153">공용 사용자 액세스 제어를 위해 정책 구성</span><span class="sxs-lookup"><span data-stu-id="7e2fe-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="7e2fe-154">페더레이션 및 공개 IM 연결을 사용하도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="7e2fe-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

