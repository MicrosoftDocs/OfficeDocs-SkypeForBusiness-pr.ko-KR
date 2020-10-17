---
title: 전역 범위 및 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet
description: 전역 범위와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet입니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba89ebe7322159027c5de765117afd366cb3dc23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545624"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>전역 범위 및 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet

 


비즈니스용 Skype Online에서는 *전역 범위* 또는 *태그 범위* (또는 *사용자 단위 범위*)에서 정책을 구성할 수 있습니다. **.Cs** cmdlet을 사용 하는 경우 범위 또는 id를 지정할 필요가 없습니다. 매개 변수를 사용 하지 않고 이러한 cmdlet 중 하나를 호출 하면 관련 항목이 모두 반환 됩니다. 예를 들어 다음 명령은 모든 외부 액세스 정책에 대 한 정보를 반환 합니다.

    Get-CsExternalAccessPolicy

반환 되는 데이터를 제한 하려는 경우 Identity 매개 변수 또는 Filter 매개 변수만 포함 해야 합니다. 예를 들어 글로벌 정책만 반환 하려면 다음 명령을 사용 합니다.

    Get-CsExternalAccessPolicy -Identity "global"

Id가 "RedmondAccessPolicy" 인 사용자별 정책을 반환 하려면 다음 명령을 사용 합니다.

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> 사용자별 정책을 참조 하는 경우 태그 <STRONG>접두사</STRONG> 는 선택 사항입니다. 접두사를 포함 하는이 구문도 사용할 수 있습니다.<BR>Get-CsExternalAccessPolicy-Identity "tag: RedmondAccessPolicy"



전역 정책 (즉, 사용자별 정책)을 제외한 모든 정책을 반환 하려면 다음 명령을 사용 합니다.

    Get-CsExternalAccessPolicy -Filter "tag:*"

다음 cmdlet은 전역 범위와 사용자별 (태그) 범위 모두에 대해 작동 합니다.

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan 플랜](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-cspresencepolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> 이름에도 불구 하 고 다이얼 플랜은 기능적인 말입니다. 이전 버전의 Lync Server에서 사용 되는 용어를 보존 하기 위해 전화 걸기 정책과 같은 용어 <EM>다이얼 플랜이</EM> 대신 사용 됩니다.



## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

