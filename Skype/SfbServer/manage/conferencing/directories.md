---
title: 비즈니스용 Skype 서버에서 전화 회의 Director 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '요약: 비즈니스용 Skype 서버에서 전화 회의를 만드는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: e4d73cc73a5c3c343e8a4734923cf80fb2590211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119477"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="da03e-103">비즈니스용 Skype 서버에서 전화 회의 Director 만들기</span><span class="sxs-lookup"><span data-stu-id="da03e-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="da03e-104">**요약:** 비즈니스용 Skype 서버에서 전화 회의를 만드는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da03e-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="da03e-105">전화 회의는 참가자가 비즈니스용 Skype를 사용할 때 전화 회의에 참가하는 데 사용하는 영수 모임 ID와 전화 접속 회의 참가자가 전화 회의에 참가하는 데 사용하는 숫자 전용 회의 ID 간의 매핑을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="da03e-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="da03e-106">회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="da03e-106">Create a conference directory</span></span>

<span data-ttu-id="da03e-107">전화 회의 디렉터리를 여러 개 만들면 상당히 많은 수의 전화 회의가 만들어질 때까지 전화 회의 ID가 짧게 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da03e-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="da03e-108">전화 회의 ID를 약 6자리로 유지하려면 사용자당 전화 회의 수가 보편적인 조직의 경우 풀의 사용자 999명당 하나의 전화 회의 디렉터리를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="da03e-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="da03e-109">이 지침에 따라 전화 회의 ID는 일반적으로 작게 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da03e-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="da03e-110">그러나 풀 전체의 전화 회의 센터 수가 9를 초과하면 추가 전화 회의를 지원하기 위해 전화 회의 ID 길이가 늘어나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da03e-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="da03e-111">회의 ID 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da03e-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="da03e-112">회의 디렉터리를 만들 경우 **New-CsConferenceDirectory** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da03e-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="da03e-113">예를 들어 다음 명령은 ID가 42인 전화 회의 디렉터리를 만듭니다. 이 디렉터리는 풀에서 atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="da03e-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="da03e-114">자세한 내용은 [New-CsConferenceDirectory 를 참조하십시오.](/powershell/module/skype/new-csconferencedirectory?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="da03e-114">For more information, see [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
