---
title: 장치 구성 새로 만들기 또는 기존 기능 편집
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
ms.openlocfilehash: b0973c73580aee3cfc81dfb79ac65613ddfcf204
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119927"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="37d18-104">장치 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="37d18-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="37d18-105">새 장치 **구성**  또는 장치 구성 편집 페이지에서 비즈니스용 Skype Phone Edition을 관리하는 데 사용되는 설정 컬렉션을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="37d18-106">이러한 설정을 사용하면 필수 보안 모드, 장치 로깅 수준, 음성 QoS(서비스 품질) 설정, 그리고 지정된 기간 동안 활동이 없으면 전화를 자동으로 잠글지 여부 등의 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="37d18-107">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="37d18-107">Tasks you can perform</span></span>

<span data-ttu-id="37d18-108">**새 장치 구성** 또는 **장치 구성 편집** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="37d18-109">새 장치 구성 추가</span><span class="sxs-lookup"><span data-stu-id="37d18-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="37d18-110">기존 장치 구성의 속성 수정</span><span class="sxs-lookup"><span data-stu-id="37d18-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="37d18-111">UI 참조</span><span class="sxs-lookup"><span data-stu-id="37d18-111">UI Reference</span></span>

<span data-ttu-id="37d18-112">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="37d18-113">**범위** 장치 구성의 범위(전역 또는 사이트)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="37d18-114">**이름** 장치 구성의 이름을 추가하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="37d18-115">**SIP 보안** 비즈니스용 Skype Phone Edition 장치에 대한 전송 및 인증 요구 사항을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="37d18-116">다음 옵션에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="37d18-117">**낮음** 모든 유형의 권한 부여 또는 전송을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="37d18-118">**보통** 사용자 인증에는 NTLM 또는 Kerberos가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="37d18-119">**높음** 사용자 인증에는 NTLM 또는 Kerberos가 필요하며 SIP 연결에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="37d18-120">**로깅 수준** UC 장치에서 로깅을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="37d18-121">사용할 수 있는 값은 사용 안 함, 낮음, 중간, 높음입니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="37d18-122">기본값은 사용 안 함입니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-122">The default value is Off.</span></span>
    
- <span data-ttu-id="37d18-123">**음성 QoS(서비스 품질)** 비즈니스용 Skype Phone Edition 장치에서 발신되는 음성 트래픽에 할당된 DSCP 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="37d18-124">기본값은 40입니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-124">The default is 40.</span></span> <span data-ttu-id="37d18-125">그러나 40은 일반적으로 오디오 트래픽에 사용되는 값이 아니며, 대신 오디오 트래픽은 거의 항상 DSCP 코드 46으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="37d18-126">네트워크 전체에서 일관성을 유지하기 위해 이 값을 46으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="37d18-127">**전화 잠금** UC 전화가 지정된 기간 동안 비활성화된 후 자동으로 잠글지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="37d18-128">구성할 수 있는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="37d18-129">**장치 잠금 적용** 이 확인란을 선택하여 장치 잠금을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="37d18-130">**최소 PIN 길이** 휴대폰 잠금을 해제하는 데 사용되는 개인식별번호(PIN)의 최소 길이를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="37d18-131">PIN 길이의 범위는 4-15자리입니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="37d18-132">기본 길이는 6자리입니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="37d18-133">**전화 잠금 시간제한** 휴대폰 자체를 잠그기 전의 최소 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="37d18-134">시간 범위는 0~60분입니다. 기본값은 10분입니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="37d18-135">값을 HH:MM:SS 형식으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37d18-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="37d18-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37d18-136">See also</span></span>

[<span data-ttu-id="37d18-137">장치 구성</span><span class="sxs-lookup"><span data-stu-id="37d18-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="37d18-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="37d18-138">Set-CsUCPhoneConfiguration</span></span>](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)