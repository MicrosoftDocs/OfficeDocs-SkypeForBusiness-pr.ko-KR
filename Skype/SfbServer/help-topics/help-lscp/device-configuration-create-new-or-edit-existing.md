---
title: 장치 구성 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: 새 장치 구성 또는 장치 구성 편집 페이지에서 비즈니스용 Skype Phone 에디션을 관리 하는 데 사용 되는 설정 모음을 만들거나 수정할 수 있습니다. 이러한 설정을 사용하면 필수 보안 모드, 장치 로깅 수준, 음성 QoS(서비스 품질) 설정, 그리고 지정된 기간 동안 활동이 없으면 전화를 자동으로 잠글지 여부 등의 옵션을 구성할 수 있습니다.
ms.openlocfilehash: 0bd8d79a97f9dd48faff09f1d7a8e0cfb41473f6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700323"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="fedeb-104">장치 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="fedeb-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="fedeb-105">**새 장치 구성** 또는 **장치 구성 편집** 페이지에서 비즈니스용 Skype Phone 에디션을 관리 하는 데 사용 되는 설정 모음을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="fedeb-106">이러한 설정을 사용하면 필수 보안 모드, 장치 로깅 수준, 음성 QoS(서비스 품질) 설정, 그리고 지정된 기간 동안 활동이 없으면 전화를 자동으로 잠글지 여부 등의 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="fedeb-107">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="fedeb-107">Tasks you can perform</span></span>

<span data-ttu-id="fedeb-108">**새 장치 구성** 또는 **장치 구성 편집** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="fedeb-109">새 장치 구성 추가</span><span class="sxs-lookup"><span data-stu-id="fedeb-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="fedeb-110">기존 장치 구성의 속성 수정</span><span class="sxs-lookup"><span data-stu-id="fedeb-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="fedeb-111">UI 참조</span><span class="sxs-lookup"><span data-stu-id="fedeb-111">UI Reference</span></span>

<span data-ttu-id="fedeb-112">다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="fedeb-113">**범위** 장치 구성의 범위 (전역 또는 사이트)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="fedeb-114">**이름** 장치 구성의 이름을 추가 하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="fedeb-115">**SIP 보안** 비즈니스용 Skype Phone Edition 장치에 대 한 전송 및 인증 요구 사항을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="fedeb-116">다음 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="fedeb-117">**낮음입니다** 모든 유형의 권한 부여 또는 전송을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="fedeb-118">**Medium** 사용자 인증에 NTLM 또는 Kerberos가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="fedeb-119">**높음** 사용자 인증에는 NTLM 또는 Kerberos가 필요 하며 SIP 연결에는 TLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="fedeb-120">**로깅 수준** UC 장치에서 로깅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="fedeb-121">사용할 수 있는 값은 사용 안 함, 낮음, 중간, 높음입니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="fedeb-122">기본값은 사용 안 함입니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-122">The default value is Off.</span></span>
    
- <span data-ttu-id="fedeb-123">**보이스 서비스 품질 (QoS)** 비즈니스용 Skype Phone Edition 장치에서 음성 트래픽 emanating에 할당 된 DSCP 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="fedeb-124">기본값은 40입니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-124">The default is 40.</span></span> <span data-ttu-id="fedeb-125">그러나 40는 일반적으로 오디오 트래픽에 사용 되는 값이 아닙니다. 대신 오디오 트래픽은 거의 항상 DSCP 코드 46으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="fedeb-126">네트워크 전체에서 일관성을 유지 하기 위해이 값을 46으로 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="fedeb-127">**전화 잠금** 지정 된 기간 동안 사용할 수 없는 경우 UC 전화기가 자동으로 잠길 지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="fedeb-128">다음은 구성할 수 있는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="fedeb-129">**장치 잠금 적용** 이 확인란을 선택 하 여 장치 잠금을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="fedeb-130">**최소 PIN 길이** 휴대폰을 잠금 해제 하는 데 사용 되는 PIN (개인 식별 번호)의 최소 길이를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="fedeb-131">PIN 길이의 범위는 4 ~ 15 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="fedeb-132">기본 길이는 6 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="fedeb-133">**전화 잠금 시간 초과** 전화가 잠기는 최소 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="fedeb-134">시간 초과의 범위는 0 ~ 60 분입니다. 기본값은 10 분입니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="fedeb-135">HH: MM: SS 형식으로 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fedeb-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fedeb-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fedeb-136">See also</span></span>

[<span data-ttu-id="fedeb-137">장치 구성</span><span class="sxs-lookup"><span data-stu-id="fedeb-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="fedeb-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="fedeb-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
