---
title: 사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 8aee680c6e55de62ff9d49724d3e480c00159aa4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755110"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="01e03-102">사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="01e03-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="01e03-103">비즈니스용 Skype Online에서 개별 사용자 Id를 참조 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="01e03-104">사용자의 Active Directory 도메인 서비스 표시 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="01e03-105">예시:</span><span class="sxs-lookup"><span data-stu-id="01e03-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="01e03-106">사용자의 SIP 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-106">Use the user’s SIP address.</span></span> <span data-ttu-id="01e03-107">예시:</span><span class="sxs-lookup"><span data-stu-id="01e03-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="01e03-108">사용자의 UPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-108">Use the user’s UPN.</span></span> <span data-ttu-id="01e03-109">예시:</span><span class="sxs-lookup"><span data-stu-id="01e03-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="01e03-110">사용자의 Active Directory 도메인 서비스 고유 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="01e03-111">예시:</span><span class="sxs-lookup"><span data-stu-id="01e03-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="01e03-112">사용자 Id를 허용 하는 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="01e03-113">[사용 안 함-Enable-csmeetingroom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-114">[Enable-Enable-csmeetingroom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-116">[Enable-csmeetingroom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-117">[Get-csonlineuser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-119">[새 전자 메일 주소](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-120">[제거-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-121">[제거-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-123">[Enable-csmeetingroom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01e03-124">[설정-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="01e03-125">사용자 Id를 지정 하지 않아도 되는 경우에는 **Cs** cmdlet 중 하나를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="01e03-126">이 경우 cmdlet은 지정 된 항목의 모든 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="01e03-127">예를 들어이 명령은 비즈니스용 Skype 온라인을 사용할 수 있도록 설정 된 모든 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="01e03-128">Identity 매개 변수는 특정 사용자에 대 한 정보를 반환 하려는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e03-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="01e03-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01e03-129">See Also</span></span>


[<span data-ttu-id="01e03-130">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="01e03-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="01e03-131">[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01e03-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

