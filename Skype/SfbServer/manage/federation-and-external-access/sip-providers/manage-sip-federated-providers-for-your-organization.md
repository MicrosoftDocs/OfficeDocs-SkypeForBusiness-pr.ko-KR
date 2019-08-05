---
title: 조직에 대한 SIP 페더레이션 공급자 관리
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP 페더레이션된 공급자의 사용자에 대 한 지원을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ee16ec8953a722a86838f710fdf92cb9b2ce5f36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197488"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="892db-103">비즈니스용 Skype 서버에서 조직의 SIP 페더레이션 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="892db-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="892db-104">SIP 페더레이션된 공급자의 사용자에 대 한 지원을 구성 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="892db-105">하나 이상의 외부 사용자 액세스 정책을 구성 하 여 SIP 페더레이션된 공급자 연락처와의 통신 지원</span><span class="sxs-lookup"><span data-stu-id="892db-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="892db-106">지원 하려는 호스트 된 공급자 지정</span><span class="sxs-lookup"><span data-stu-id="892db-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="892db-107">지원 하려는 공용 IM 공급자 지정</span><span class="sxs-lookup"><span data-stu-id="892db-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="892db-108">비즈니스용 Skype 서버에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="892db-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="892db-109">공용 인스턴트 메시징 (IM) 연결은 조직의 사용자가 IM을 사용 하 여 공개 공급자가 제공 하는 IM 서비스 사용자와 통신할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="892db-110">비즈니스용 Skype Server에는 인스턴트 메시지를 위한 공용 공급자 구성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="892db-111">각 공용 공급자는 공급자의 Edge 서버 정규화 된 도메인 이름으로 구성 되며, 기본 확인 수준을 **통해 사용자는이 공급자를 사용 하는 대화 상대 목록에 있는 사용자와만 통신할 수**있습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="892db-112">기본 설정으로는 공용 공급자가 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="892db-113">공용 공급자를 사용 하도록 설정 하기 전에 라이선스 계약 및 프로비저닝 작업을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="892db-114">라이선스 및 프로비저닝 작업을 완료 하기 전에 공급자를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="892db-115">필수 작업 시간이 완료 될 때까지 사용자는 해당 공급자의 대화 상대와 통신할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="892db-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="892db-116">공용 공급자의 라이선스 및 프로비저닝에 대 한 자세한 내용은 [공용 사용자 액세스를 제어 하는 정책 구성을](../external-access-policies/configure-policies-to-control-public-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="892db-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="892db-117">다음 절차를 사용 하 여 공용 공급자를 만들거나 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="892db-118">공용 공급자를 만들거나 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="892db-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="892db-119">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="892db-120">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="892db-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="892db-121">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **SIP 페더레이션된 공급자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="892db-122">새 공용 공급자를 만들어야 하는 경우 **새로 만들기** 를 클릭 한 다음 **공용 공급자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="892db-123">공용 공급자 목록에서 항목을 편집 해야 하는 경우에는 공용 공급자를 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="892db-124">**SIP 페더레이션 공급자 편집** 페이지에서 다음 설정을 입력 하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="892db-125">**이 공급자**   와 통신 사용이 설정을 선택 하면이 공급자의 사용자와의 IM이 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="892db-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="892db-126">**공급자 이름:**   필요한 속성에는 공급자 이름을 SIP 페더레이션된 공급자 목록에 반영할 형식으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="892db-127">**FQDN (액세스에 지 서비스):**   필수 속성인 경우 구성 중인 공급자의 액세스에 지 서비스에 대 한 정규화 된 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="892db-128">이 정보는 기본 항목으로 제공 되며 공용 공급자가 공용 공급자에서 액세스 경계 서비스의 FQDN을 변경할 경우에만 변경 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="892db-129">**기본 확인 수준:**    **이 공급자를 사용 하는 사용자가 대화 상대 목록에 있는 사용자와 통신할 수 있도록 허용** 하는 기본 설정은 수락 하 고 연락처 목록에 있는 연락처와의 통신을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="892db-130">**사용자가이 공급자를 사용 하는 모든 사용자와 통신 하도록 허용을** 선택 하면 연락처 초대를 받아서 수락 해야 하는 제한이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="892db-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="892db-131">이 설정은 공용 공급자의 네트워크에서 사용자에 게 연락할 수 있는 사용자를 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="892db-132">설정 구성을 완료 했으면 **커밋을** 클릭 하 여 저장 하거나 **취소** 를 클릭 하 여 변경 내용을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="892db-133">비즈니스용 Skype 서버에서 호스트 된 SIP 페더레이션 공급자 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="892db-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="892db-134">호스트 된 공급자 IM (인스턴트 메시징) 연결을 사용 하면 조직의 사용자가 호스팅된 공급자가 제공 하는 IM 서비스 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="892db-135">각 호스팅된 공급자는 공급자의 Edge 서버 정규화 된 도메인 이름으로 구성 되며, 기본 확인 수준을 **통해 사용자는이 공급자를 사용 하는 대화 상대 목록에 있는 사용자와만 통신할 수**있습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="892db-136">다음 절차를 사용 하 여 호스팅 공급자를 만들거나 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="892db-137">호스팅된 공급자를 만들거나 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="892db-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="892db-138">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="892db-139">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="892db-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="892db-140">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **SIP 페더레이션된 공급자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="892db-141">호스트 된 새 공급자를 만들어야 하는 경우 **새로 만들기** 를 클릭 한 다음 **호스팅된 공급자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="892db-142">호스트 된 공급자 목록에서 항목을 편집 해야 하는 경우에는 호스팅 공급자를 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="892db-143">**SIP 페더레이션 공급자 편집** 페이지에서 다음 설정을 입력 하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="892db-144">**이 공급자**   와 통신 사용이 설정을 선택 하면이 공급자의 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="892db-145">**공급자 이름:**   필요한 속성에는 공급자 이름을 SIP 페더레이션된 공급자 목록에 반영할 형식으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="892db-146">**FQDN (액세스에 지 서비스):**   필수 속성인 경우 구성 중인 호스트 된 공급자의 액세스에 지 서비스에 대 한 정규화 된 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="892db-147">이 정보는 호스팅된 공급자가 제공 해야 하며 호스팅된 공급자가 호스트 된 공급자에 대 한 액세스 경계 서비스의 FQDN을 변경 하는 경우에만 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="892db-148">**기본 확인 수준:**    **이 공급자를 사용 하는 사용자가 대화 상대 목록에 있는 사용자와 통신할 수 있도록 허용** 하는 기본 설정은 수락 하 고 연락처 목록에 있는 연락처와의 통신을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="892db-149">**사용자가이 공급자를 사용 하는 모든 사용자와 통신 하도록 허용을** 선택 하면 연락처 초대를 받아서 수락 해야 하는 제한이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="892db-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="892db-150">이 설정은 호스팅된 공급자의 네트워크에서 사용자에 게 연락할 수 있는 사용자를 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="892db-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="892db-151">설정 구성을 완료 했으면 **커밋을** 클릭 하 여 저장 하거나 **취소** 를 클릭 하 여 변경 내용을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="892db-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="892db-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="892db-152">See Also</span></span>


[<span data-ttu-id="892db-153">공용 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="892db-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="892db-154">페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="892db-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

