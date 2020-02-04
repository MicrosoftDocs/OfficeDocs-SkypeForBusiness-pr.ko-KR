---
title: 사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c29eb2aadefcb6a9f3ca9b5c11a49f7e41167a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728128"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="aefea-102">사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="aefea-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="aefea-103">비즈니스용 Skype Online에는 개별 사용자 Id를 참조 하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="aefea-104">사용자의 Active Directory 도메인 서비스 표시 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="aefea-105">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="aefea-106">사용자의 SIP 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-106">Use the user’s SIP address.</span></span> <span data-ttu-id="aefea-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="aefea-108">사용자의 UPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-108">Use the user’s UPN.</span></span> <span data-ttu-id="aefea-109">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="aefea-110">사용자의 Active Directory 도메인 서비스 고유 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="aefea-111">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="aefea-112">다음 cmdlet은 사용자 Id를 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="aefea-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-115">[Get-C(Um연락처)](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-119">[신규-C또는 Um연락처](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-120">[제거-C간 Umcontact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-121">[제거-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-122">[Set-C간 Umcontact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="aefea-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="aefea-125">**Cs** cmdlet 중 하나를 호출할 때 사용자 id를 지정 하지 않아도 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="aefea-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="aefea-126">이 경우 cmdlet은 지정 된 항목의 모든 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="aefea-127">예를 들어이 명령은 비즈니스용 Skype Online에 대해 사용 하도록 설정 된 모든 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="aefea-128">Id 매개 변수는 특정 사용자에 대 한 정보를 반환 하려는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="aefea-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="aefea-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aefea-129">See Also</span></span>


[<span data-ttu-id="aefea-130">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="aefea-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="aefea-131">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aefea-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

