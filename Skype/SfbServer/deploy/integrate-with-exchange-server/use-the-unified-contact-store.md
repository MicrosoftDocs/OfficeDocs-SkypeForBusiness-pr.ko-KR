---
title: 통합 비즈니스용 Skype 서버 사용하도록 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: '요약: 통합 연락처 저장소를 구성하여 Exchange Server 비즈니스용 Skype 서버.'
ms.openlocfilehash: 78953049394391517d229205e711e670701d9f857458673646e4022a178d3843
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295715"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>통합 비즈니스용 Skype 서버 사용하도록 구성
 
**요약:** 2016 또는 Exchange Server 2013 및 Exchange Server 통합 연락처 저장소를 비즈니스용 Skype 서버.
  
사용자는 통합 연락처 저장소를 사용하여 단일 연락처 목록을 유지 관리한 다음 비즈니스용 Skype, Microsoft Outlook 2013 및 Microsoft Outlook Web App 2013을 비롯한 여러 응용 프로그램에서 해당 연락처를 사용할 수 있도록 합니다. 사용자에 대해 통합 연락처 저장소를 사용하도록 설정하면 해당 사용자의 연락처가 비즈니스용 Skype 서버 저장되지 않습니다. 대신 연락처는 Exchange Server 2016 또는 Exchange Server 2013에 저장되고 Exchange 검색됩니다.
  
> [!NOTE]
> 기술적으로 연락처 정보는 사용자의 사서함에 있는 폴더 쌍에 Exchange 저장됩니다. 연락처 자체는 최종 사용자에게 표시되는 비즈니스용 Skype 폴더에 저장됩니다. 연락처에 대한 메타데이터는 최종 사용자에게 표시되지 않는 하위 파일에 저장됩니다. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>사용자에 대해 통합 연락처 저장소 사용

비즈니스용 Skype 서버 및 Exchange Server 서버 간 인증이 이미 구성되어 있는 경우 통합 연락처 저장소도 사용하도록 설정한 것입니다. 추가 서버 구성이 필요하지 않습니다. 그러나 사용자의 연락처를 통합 연락처 저장소로 이동하려면 추가 사용자 계정 구성이 필요합니다. 기본적으로 사용자 연락처는 통합 비즈니스용 Skype 서버 저장소에 보관되지 않습니다.
  
통합 연락처 저장소에 대한 액세스는 사용자 서비스 정책을 사용하여 비즈니스용 Skype 서버 관리됩니다. 사용자 서버 정책에는 단일 속성(UcsAllowed)만 있습니다. 이 속성은 사용자의 연락처가 저장되는 위치를 확인하는 데 사용됩니다. 사용자가 UcsAllowed가 True($True)로 설정된 사용자 서비스 정책에 의해 관리되는 경우 사용자의 연락처는 통합 연락처 저장소에 저장됩니다. 사용자가 UcsAllowed가 False($False)로 설정된 사용자 서비스 정책에 의해 관리되는 경우 해당 사용자의 연락처는 비즈니스용 Skype 서버.
  
전역 비즈니스용 Skype 서버 단일 사용자 서비스 정책(전역 범위에서 구성)도 설치됩니다. 이 정책의 UcsAllowed 값은 True로 설정되어 있습니다. 즉, 기본적으로 사용자 연락처는 통합 연락처 저장소에 저장됩니다(배포 및 구성된 경우). 모든 사용자 연락처를 통합 연락처 저장소로 마이그레이션하려는 경우 아무 것도 할 수 없습니다. 
  
모든 연락처를 통합 연락처 저장소로 마이그레이션하지 않도록 설정하려면 전역 정책에서 UcsAllowed 속성을 False로 설정하여 모든 사용자에 대해 통합 연락처 저장소를 사용하지 않도록 설정할 수 있습니다.
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

전역 정책에서 통합 연락처 저장소를 사용하지 않도록 설정한 후 통합 연락처 저장소를 사용할 수 있도록 하는 사용자당 정책을 만들 수 있습니다. 이렇게 하면 일부 사용자가 통합 연락처 저장소에 자신의 연락처를 보관하고 다른 사용자는 계속해서 통합 연락처 저장소에 연락처를 유지할 수 비즈니스용 Skype 서버. 다음 명령을 사용하여 사용자당 사용자 서비스 정책을 만들 수 있습니다.
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

새 정책을 만든 후 통합 연락처 저장소에 액세스할 수 있어야 하는 사용자에게 해당 정책을 할당해야 합니다. 사용자당 정책은 다음 명령을 사용하여 사용자에게 할당할 수 있습니다.
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

정책이 할당된 비즈니스용 Skype 서버 사용자의 연락처를 통합 연락처 저장소로 마이그레이션하기 시작할 수 있습니다. 마이그레이션이 완료되면 사용자는 자신의 연락처가 Exchange 저장되지 비즈니스용 Skype 서버. 마이그레이션이 완료될 때 Lync 2013에 로그온할 경우 메시지 상자가 나타나고 비즈니스용 Skype 로그오프한 다음 다시 로그온하여 프로세스를 완료할 수 있습니다. 이 사용자 정책이 할당되지 않은 사용자는 해당 연락처를 통합 연락처 저장소로 마이그레이션하지 않습니다. 이러한 사용자는 글로벌 정책에 의해 관리되고 통합 연락처 저장소를 전역 정책에서 사용할 수 없습니다.
  
비즈니스용 Skype 서버 관리 셸 내에서 [Test-CsUnifiedContactStore](/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) cmdlet을 실행하여 사용자의 연락처가 통합 연락처 저장소로 마이그레이션된 경우를 확인할 수 있습니다.
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

이 Test-CsUnifiedContactStore 성공하면 sip:kenmyer@ .com 사용자의 연락처가 통합 연락처 저장소로 <span></span> <span></span> 마이그레이션된 것입니다.
  
## <a name="rolling-back-the-unified-contact-store"></a>통합 연락처 저장소 롤백

통합 연락처 저장소에서 사용자의 연락처를 제거해야 하는 경우(예: 사용자가 Microsoft Lync Server 2010에서 다시 연결되어야 하여 통합 연락처 저장소를 더 이상 사용할 수 없는 경우) 두 가지 작업을 해야 합니다. 먼저 사용자에게 통합 연락처 저장소에 연락처 저장을 금지하는 새 사용자 서비스 정책을 할당해야 합니다. 즉, UcsAllowed 속성이 $False. 이러한 정책이 없는 경우 이와 유사한 명령을 사용하여 정책을 만들 수 있습니다.
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

그런 다음 다음 명령을 사용하여 이 새 사용자당 정책(NoUnifiedContactStore)을 할당할 수 있습니다.
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

위의 명령은 사용자 Ken Myer에게 새 정책을 할당하고 Ken의 연락처가 통합 연락처 저장소로 마이그레이션되지 않도록 합니다.
  
> [!NOTE]
> 경우에 따라 사용자의 현재 사용자 서비스 정책 할당을 단순히 할당하지 말고 동일한 순 효과를 얻을 수 있습니다. 예를 들어 Ken Myer에게 통합 연락처 저장소를 사용할 수 있도록 하는 사용자당 사용자 서비스 정책이 있지만 전역 정책에 따라 통합 연락처 저장소를 사용할 수 없는 경우를 가정해 보겠습니다. 이 경우 Ken의 사용자당 서비스 정책을 할당을 해지할 수 있습니다. 이렇게 하면 Ken이 전역 정책에 의해 자동으로 관리되어 통합 연락처 저장소에 더 이상 액세스할 수 없습니다. 이전에 할당된 사용자당 정책을 할당하지 않은 경우 이전과 동일한 명령을 사용하지만 이번에는 PolicyName 매개 변수를 null 값으로 설정합니다. Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null 
  
"Ken의 연락처가 통합 연락처 저장소로 마이그레이션되지 않도록 방지"라는 용어는 통합 연락처 저장소로 작업할 때 유의해야 합니다. 단순히 Ken을 새 사용자 서비스 정책을 할당하면 연락처가 통합 연락처 저장소에서 이동되지 않습니다. 사용자가 비즈니스용 Skype 서버 로그온하면 시스템에서 사용자의 사용자 서비스 정책을 확인하여 자신의 연락처를 통합 연락처 저장소에 보관해야 하는지 여부를 확인할 수 있습니다. 예(UcsAllowed 속성이 $True)이면 해당 연락처가 통합 연락처 저장소에 아직 없는 경우 해당 연락처가 통합 연락처 저장소로 마이그레이션됩니다. 대답이 아니요인 경우 비즈니스용 Skype 서버 단순히 사용자의 연락처를 무시하고 다음 작업으로 이동하게 됩니다. 즉, 비즈니스용 Skype 서버 UcsAllowed 속성 값에 관계없이 사용자의 연락처를 통합 연락처 저장소에서 자동으로 이동하지 않습니다.
  
즉, 사용자에게 새 사용자 서비스 정책을 할당한 후 [Invoke-CsUcsRollback](/powershell/module/skype/invoke-csucsrollback?view=skype-ps) cmdlet을 실행하여 사용자의 연락처를 새 사용자 Exchange Server 다시 비즈니스용 Skype 서버. 예를 들어 새 사용자 서비스 정책을 Ken Myer에게 할당한 후 다음 명령을 사용하여 연락처를 통합 연락처 저장소에서 이동할 수 있습니다.
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

사용자 서비스 정책을 변경했지만 실행하지 Invoke-CsUcsRollback Ken의 연락처는 통합 연락처 저장소에서 제거되지 않습니다. Ken Myer의 Invoke-CsUcsRollback 서비스 정책을 변경하지 않는 경우 어떻게 하나요? 이 경우 Ken의 연락처가 통합 연락처 저장소에서 일시적으로 제거됩니다. 이 제거는 일시적으로만 사용하다는 점에 유의해야 합니다. Ken의 연락처가 통합 연락처 저장소에서 제거된 후 비즈니스용 Skype 서버 7일간 기다렸다가 Ken에게 할당된 사용자 서비스 정책을 확인할 수 있습니다. Ken에게 여전히 통합 연락처 저장소의 사용자를 사용할 수 있는 정책이 할당되어 있는 경우 Ken의 연락처는 자동으로 다시 연락처 저장소로 이동됩니다. 통합 연락처 저장소에서 연락처를 영구적으로 제거하려면 사용자 서비스 정책과 통합 연락처 cmdlet을 Invoke-CsUcsRollback 변경해야 합니다.
  
마이그레이션에 영향을 줄 수 있는 변수 수가 되기 때문에 계정을 통합 연락처 저장소로 완전히 마이그레이션하는 데 얼마나 오래 걸릴지 예측하기가 어렵습니다. 그러나 일반적으로 마이그레이션은 즉시 적용되지 않습니다. 적은 수의 연락처를 마이그레이션하는 경우에도 이동이 완료되기까지 10분 이상 걸릴 수 있습니다.
