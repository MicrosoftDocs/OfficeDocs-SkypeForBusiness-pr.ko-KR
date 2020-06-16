---
title: 회의 공급자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accaad94f5e29863ac948ea64d061d23b811105f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755130"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="4b5fd-102">회의 공급자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="4b5fd-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="4b5fd-103">조직이 계약 한 모든 오디오 회의 공급자에 대 한 정보를 반환 하려면 다음 매개 변수를 사용 하지 않고 [test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet을 호출 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b5fd-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="4b5fd-104">반환 된 데이터를 단일 공급자 (이 예제에서는 Contoso Audio Services 공급자)로 제한 하려면 Identity 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b5fd-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="4b5fd-105">오디오 회의 공급자 ID를 허용 하는 비즈니스용 Skype 온라인 cmdlet은 한 명만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b5fd-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="4b5fd-106">[Test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4b5fd-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="4b5fd-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b5fd-107">See Also</span></span>


[<span data-ttu-id="4b5fd-108">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="4b5fd-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="4b5fd-109">[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4b5fd-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

