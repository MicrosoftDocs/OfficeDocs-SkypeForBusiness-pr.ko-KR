---
title: 장치 구성 새로 만들기 또는 기존 데이터 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: 새 장치 구성 또는 장치 구성 편집 페이지에서 비즈니스용 Skype Phone Edition을 관리하는 데 사용되는 설정 컬렉션을 만들거나 수정할 수 있습니다. 이러한 설정을 사용하면 필수 보안 모드, 장치 로깅 수준, 음성 QoS(서비스 품질) 설정, 그리고 지정된 기간 동안 활동이 없으면 전화를 자동으로 잠글지 여부 등의 옵션을 구성할 수 있습니다.
ms.openlocfilehash: ba84c6b9f820d0130940fce4dadad1cd38e7efec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807308"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="43fc0-104">장치 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="43fc0-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="43fc0-105">새 장치 **구성**  또는 장치 구성 편집 페이지에서 비즈니스용 Skype Phone Edition을 관리하는 데 사용되는 설정 컬렉션을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="43fc0-106">이러한 설정을 사용하면 필수 보안 모드, 장치 로깅 수준, 음성 QoS(서비스 품질) 설정, 그리고 지정된 기간 동안 활동이 없으면 전화를 자동으로 잠글지 여부 등의 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="43fc0-107">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="43fc0-107">Tasks you can perform</span></span>

<span data-ttu-id="43fc0-108">**새 장치 구성** 또는 **장치 구성 편집** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="43fc0-109">새 장치 구성 추가</span><span class="sxs-lookup"><span data-stu-id="43fc0-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="43fc0-110">기존 장치 구성의 속성 수정</span><span class="sxs-lookup"><span data-stu-id="43fc0-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="43fc0-111">UI 참조</span><span class="sxs-lookup"><span data-stu-id="43fc0-111">UI Reference</span></span>

<span data-ttu-id="43fc0-112">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="43fc0-113">**범위** 장치 구성의 범위(전역 또는 사이트)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="43fc0-114">**이름** 장치 구성의 이름을 추가하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="43fc0-115">**SIP 보안** 비즈니스용 Skype Phone Edition 장치에 대한 전송 및 인증 요구 사항을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="43fc0-116">다음 옵션에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="43fc0-117">**낮음** 모든 유형의 권한 부여 또는 전송을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="43fc0-118">**보통** 사용자 인증에는 NTLM 또는 Kerberos가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="43fc0-119">**높음** NTLM 또는 Kerberos는 사용자 인증에 필요하고 SIP 연결에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="43fc0-120">**로깅 수준** UC 장치에서 로깅을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="43fc0-121">사용할 수 있는 값은 사용 안 함, 낮음, 중간, 높음입니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="43fc0-122">기본값은 사용 안 함입니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-122">The default value is Off.</span></span>
    
- <span data-ttu-id="43fc0-123">**음성 QoS(서비스 품질)** 비즈니스용 Skype Phone Edition 장치에서 발신되는 음성 트래픽에 할당된 DSCP 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="43fc0-124">기본값은 40입니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-124">The default is 40.</span></span> <span data-ttu-id="43fc0-125">그러나 40은 오디오 트래픽에 일반적으로 사용되는 값이 아니며, 대신 오디오 트래픽은 거의 항상 DSCP 코드 46으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="43fc0-126">네트워크 전체에서 일관성을 유지 관리하기 위해 이 값을 46으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="43fc0-127">**전화 잠금** UC 전화가 지정된 기간 동안 비활성화된 후 자동으로 잠글지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="43fc0-128">구성할 수 있는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="43fc0-129">**장치 잠금 적용** 이 확인란을 선택하여 장치 잠금을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="43fc0-130">**최소 PIN 길이** 휴대폰 잠금을 해제하는 데 사용되는 개인식별번호(PIN)의 최소 길이를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="43fc0-131">PIN 길이의 범위는 4-15자리입니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="43fc0-132">기본 길이는 6자리입니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="43fc0-133">**전화 잠금 시간** 휴대폰 자체를 잠그기 전의 최소 기간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="43fc0-134">시간 범위는 0~60분입니다. 기본값은 10분입니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="43fc0-135">HH:MM:SS 형식으로 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc0-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="43fc0-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43fc0-136">See also</span></span>

[<span data-ttu-id="43fc0-137">장치 구성</span><span class="sxs-lookup"><span data-stu-id="43fc0-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="43fc0-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="43fc0-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
