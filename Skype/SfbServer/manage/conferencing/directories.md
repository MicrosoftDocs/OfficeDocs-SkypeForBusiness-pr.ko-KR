---
title: 비즈니스용 Skype 서버에서 전화 회의 디렉터리 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '요약: 비즈니스용 Skype 서버에서 전화 회의 디렉터리를 만드는 방법에 대해 알아보세요.'
ms.openlocfilehash: 368248f18291b049b3478f20d3de4a11d4ae6f1c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818569"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="d6653-103">비즈니스용 Skype 서버에서 전화 회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="d6653-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="d6653-104">**요약:** 비즈니스용 Skype 서버에서 전화 회의 디렉터리를 만드는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d6653-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="d6653-105">회의 디렉터리는 비즈니스용 Skype를 사용할 때 참가자가 전화 회의에 참가 하는 데 사용 하는 영숫자 모임 ID와 전화 접속 회의 참가자가 회의에 참가 하는 데 사용 하는 숫자 전용 회의 ID 간의 매핑을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6653-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="d6653-106">회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="d6653-106">Create a conference directory</span></span>

<span data-ttu-id="d6653-107">여러 회의 디렉터리를 만들면 회의 Id가 매우 많은 회의를 만들 때까지 짧은 시간 동안 유지 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6653-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="d6653-108">사용자 당 일반적인 회의 수가 있는 조직에서 풀의 모든 999 사용자에 대해 하나의 회의 디렉터리를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6653-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="d6653-109">이 지침을 사용 하 여 회의 Id를 일반적으로 작게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6653-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="d6653-110">그러나, 풀 전체의 회의 디렉터리 수가 9 개를 초과 하면 추가 회의를 지원 하기 위해 회의 ID 길이가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="d6653-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="d6653-111">전화 회의 ID의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6653-111">The format of a conference ID is as follows:</span></span> 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="d6653-112">컨퍼런스 디렉터리를 만들려면 **CsConferenceDirectory** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6653-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="d6653-113">예를 들어 다음 명령은 id 42를 사용 하 여 풀 atl-cs-001.litwareinc.com에서 호스트 되는 컨퍼런스 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6653-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="d6653-114">자세한 내용은 [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6653-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

