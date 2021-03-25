---
title: Microsoft Teams 모임에서 전화 번호 마스크
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 모임에서 전화 번호를 마스크하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117716"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="ce703-103">Microsoft Teams 모임에서 전화 번호 마스크</span><span class="sxs-lookup"><span data-stu-id="ce703-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="ce703-104">개인 정보 보호를 강화하기 위해 오디오 회의를 사용하여 Teams 모임에 전화 접속하는 참가자의 전화 번호가 내부 참가자에게 완전히 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="ce703-105">이 숫자는 조직 외부의 참가자로부터 마스킹됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="ce703-106">이 설정은 모든 조직의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="ce703-107">마스크된 숫자는 다음 이미지와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-107">The masked number is displayed as shown in the following image:</span></span>

![마스크된 전화 번호의 예](media/hiddenPhoneNum.png)

<span data-ttu-id="ce703-109">특정 산업 사용 사례의 경우 관리자는 테넌트에서 구성된 모임에 오디오 회의 참가자의 전화 번호가 나타나는 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="ce703-110">관리자는 다음 세 가지 옵션 중 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="ce703-111">전화 번호는 외부 참가자에서만 마스킹됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="ce703-112">모임 이끌이의 테넌트에 속한 참가자는 여전히 전체 전화 번호를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="ce703-113">전화 번호는 이끌이를 제외한 모임의 모든 사람이 마스킹됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="ce703-114">전화 번호는 마스킹되지 않은 경우 모임의 모든 사람이 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="ce703-115">이 설정은 전화 번호가 노출되는 모임의 모든 표면에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="ce703-116">Microsoft PowerShell을 사용하여 전화 번호 마스킹 설정</span><span class="sxs-lookup"><span data-stu-id="ce703-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="ce703-117">PSTN(공용 전환 전화 네트워크) 마스킹 설정을 변경하기 위해 **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet의 매개 변수를 사용 가능한 옵션 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="ce703-118">외부 참가자에서만 전화 번호를 마스크하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="ce703-119">모임의 모든 참가자(이끌이 제외)의 전화 번호를 마스크하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="ce703-120">전화 번호 마스킹을 사용하지 않도록 설정하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce703-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```