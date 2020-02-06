---
title: 통합 연락처 저장소를 사용하도록 비즈니스용 Skype 서버 2015 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: Exchange Server 및 비즈니스용 Skype 서버용 통합 된 연락처 저장소를 구성 합니다.'
ms.openlocfilehash: 1719b8e8e5d99b8ef24da32111b69b1f9f847538
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796999"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>통합 연락처 저장소를 사용하도록 비즈니스용 Skype 서버 2015 구성
 
**요약:** Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버용 통합 된 연락처 저장소를 구성 합니다.
  
통합 된 연락처 저장소를 사용 하는 경우 사용자는 단일 대화 상대 목록을 유지 관리 하 고 비즈니스용 Skype, Microsoft Outlook 2013 및 Microsoft Outlook Web App 2013을 포함 하 여 여러 응용 프로그램에서 해당 연락처를 사용할 수 있습니다. 사용자에 대해 통합 된 연락처 저장소를 사용 하도록 설정 하면 해당 사용자의 연락처가 비즈니스용 Skype 서버에 저장 되지 않고 필요에 따라 검색 되지 않습니다. 대신 exchange Server 2016 또는 Exchange Server 2013에 저장 되며 Exchange 웹 서비스를 사용 하 여 검색 됩니다.
  
> [!NOTE]
> 기술적으로 연락처 정보는 사용자의 Exchange 사서함에 있는 한 쌍의 폴더에 저장 됩니다. 연락처는 최종 사용자에 게 표시 되는 비즈니스용 Skype 연락처 라는 폴더에 저장 됩니다. 연락처에 대 한 메타 데이터는 최종 사용자에 게 표시 되지 않는 하위 폴더에 저장 됩니다. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>사용자에 대해 통합 된 연락처 저장소 사용

비즈니스용 Skype 서버와 Exchange Server 간에 서버 간 인증이 이미 구성 되어 있으면 통합 된 연락처 저장소도 사용할 수 있습니다. 추가 서버 구성은 필요 하지 않습니다. 그러나 사용자의 연락처를 통합 대화 상대 저장소로 이동 하려면 추가 사용자 계정 구성이 필요 합니다. 기본적으로 사용자 연락처는 통합 된 연락처 저장소가 아닌 비즈니스용 Skype 서버에 보관 됩니다.
  
통합 된 연락처 저장소에 대 한 액세스는 비즈니스용 Skype 서버 사용자 서비스 정책을 사용 하 여 관리 됩니다. 사용자 서버 정책에는 단일 속성 (일부는 허용 되지 않음)만 있습니다. 이 속성은 사용자의 연락처가 저장 되는 위치를 확인 하는 데 사용 됩니다. 사용자가 a를 True ($True)로 설정한 사용자 서비스 정책에 따라 관리 되는 경우 사용자의 연락처가 통합 대화 상대 저장소에 저장 됩니다. 사용자가 a를 False ($False)로 설정한 사용자 서비스 정책에 따라 관리 되는 경우 비즈니스용 Skype Server에 연락처가 저장 됩니다.
  
비즈니스용 Skype Server를 설치할 때 전역 범위에서 구성 된 단일 사용자 서비스 정책도 설치 됩니다. 이 정책에서 사용할 수 있는 값이 True로 설정 되어 있으며,이는 기본적으로 사용자 연락처가 통합 된 연락처 저장소에 저장 됨을 의미 합니다 (이를 배포 하 고 구성한 경우). 모든 사용자 연락처를 통합 대화 상대 저장소로 마이그레이션하려면 아무런 작업도 수행 하지 않아도 됩니다. 
  
모든 연락처를 통합 된 연락처 저장소로 마이그레이션하지 않으려면 전역 정책의 작업을 False로 설정 하 여 모든 사용자에 대해 통합 된 연락처 저장소를 사용 하지 않도록 설정할 수 있습니다.
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

전역 정책에서 통합 된 연락처 저장소를 사용 하지 않도록 설정한 후에는 통합 된 연락처 저장소를 사용 하도록 설정 하는 사용자별 정책을 만들 수 있습니다. 이렇게 하면 다른 사용자가 비즈니스용 Skype 서버에서 연락처를 계속 유지 하면서 통합 된 연락처 저장소에 연락처를 유지할 수 있습니다. 다음과 같은 명령을 사용 하 여 사용자별 사용자 서비스 정책을 만들 수 있습니다.
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

새 정책을 만든 후에는 통합 된 연락처 저장소에 대 한 액세스 권한이 있는 모든 사용자에 게 해당 정책을 할당 해야 합니다. 사용자 단위 정책은 다음과 같은 명령을 사용 하 여 사용자에 게 할당할 수 있습니다.
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

정책이 지정 된 후 비즈니스용 Skype Server는 사용자의 연락처를 통일 된 연락처 저장소로 마이그레이션하기 시작 합니다. 마이그레이션이 완료 되 면 사용자는 비즈니스용 Skype 서버 대신 Exchange에 저장 된 연락처를 갖게 됩니다. 마이그레이션이 완료 될 때 사용자가 Lync 2013에 로그온 되어 있는 경우 메시지 상자가 표시 되 고 프로세스를 완료 하기 위해 비즈니스용 Skype를 로그 오프 하 고 다시 로그온 하 라는 메시지가 나타납니다. 이 사용자별 정책에 할당 되지 않은 사용자의 연락처는 통합 된 연락처 저장소로 마이그레이션되지 않습니다. 그 이유는 해당 사용자는 전역 정책에 따라 관리 되 고 있으며, 통합 된 대화 상대 저장소는 전역 정책에서 사용 하지 않도록 설정 되었기 때문입니다.
  
비즈니스용 Skype Server Management Shell 내에서 [CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) cmdlet을 실행 하 여 사용자의 연락처가 통합 된 연락처 저장소로 성공적으로 마이그레이션 되었는지 확인할 수 있습니다.
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Test-CsUnifiedContactStore가 성공 하면 사용자 sip: kenmyer@<span></span>litwareinc<span></span>에 대 한 연락처가 통합 대화 저장소로 마이그레이션 되었음을 의미 합니다.
  
## <a name="rolling-back-the-unified-contact-store"></a>통합 된 대화 상대 저장소 롤백

통합 된 연락처 저장소에서 사용자의 연락처를 제거 해야 하는 경우 (예: 사용자가 Microsoft Lync Server 2010을 기반으로 하 여 더 이상 통합 된 연락처 저장소를 사용할 수 없는 경우) 두 가지 작업을 수행 해야 합니다. 먼저, 통합 된 연락처 저장소에 연락처 저장을 금지 하는 새 사용자 서비스 정책을 사용자에 게 할당 해야 합니다. (즉, 여러 부분을 허용 하는 속성을 $False로 설정한 정책) 이러한 정책이 없는 경우 다음과 같은 명령을 사용 하 여 만들 수 있습니다.
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

그러면 다음과 같은 명령을 사용 하 여이 새로운 사용자별 정책 (NoUnifiedContactStore)을 할당할 수 있습니다.
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

앞의 명령은 사용자: 진구 Myer에 새 정책을 할당 하 고: 진구의 연락처를 통합 대화 상대 저장소로 마이그레이션하는 것도 방지 합니다.
  
> [!NOTE]
> 경우에 따라 사용자의 현재 사용자 서비스 정책 할당을 취소 하 여 동일한 네트워크 효과를 얻을 수 있습니다. 예를 들어: 진구 Myer에는 통합 대화 상대 저장소를 사용할 수 있는 사용자 단위 정책이 있지만, 전역 정책은 통합 된 연락처 저장소의 사용을 금지 한다고 가정 합니다. 이 경우: 진구의 사용자 단위 서비스 정책을 할당 취소할 수 있습니다. 이렇게 하면: 진구이 전역 정책에 의해 자동으로 관리 되므로 더 이상 통합 된 연락처 저장소에 액세스할 수 없습니다. 이전에 할당 된 사용자별 정책에 할당을 취소 하려면 앞에서 설명한 것과 동일한 명령을 사용 하 되, 이번에는 PolicyName 매개 변수를 null 값으로 설정 합니다.-Csuser서비스 정책-Id ": 진구 Myer"-PolicyName $Null 
  
": 진구의 연락처를 통합 된 연락처 저장소로 마이그레이션하는 것을 금지" 라는 용어는 통합 된 연락처 저장소를 사용할 때 염두에 두어야 합니다. 새 사용자 서비스 정책: 진구 지정 하기만 해도 연락처가 통합 대화 상대 저장소 밖으로 이동 하지 않습니다. 사용자가 비즈니스용 Skype 서버에 로그온 하면 시스템에서 사용자의 사용자 서비스 정책을 확인 하 여 해당 연락처를 통합 대화 상대 저장소에 보관할지 여부를 확인 합니다. 대답이 yes 인 경우 (즉, (즉, to Sallowed 속성이 $True로 설정 된 경우) 해당 연락처는 통합 된 연락처 저장소로 마이그레이션됩니다 (해당 연락처가 아직 통합 대화 저장소에 있지 않은 경우). 아니오로 대답 한 경우 비즈니스용 Skype 서버는 사용자의 연락처를 무시 하 고 다음 작업으로 이동 합니다. 이는 비즈니스용 Skype 서버는 c 지 속성 값에 관계 없이 사용자의 연락처를 통합 된 연락처 저장소 밖으로 자동으로 이동 하지 않음을 의미 합니다.
  
즉, 사용자에 게 새 사용자 서비스 정책을 할당 한 후에는 [CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) cmdlet을 실행 하 여 사용자의 연락처를 Exchange server 외부로 이동 하 고 비즈니스용 Skype server로 다시 전환 해야 합니다. 예를 들어 새 사용자 서비스 정책에: 진구 Myer를 할당 한 후 다음 명령을 사용 하 여 연락처를 통합 된 연락처 저장소 외부로 이동할 수 있습니다.
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

사용자 서비스 정책을 변경 했지만 실행 하지 않는 경우 CsUcsRollback cmdlet: 진구의 연락처는 통합 된 연락처 저장소에서 제거 되지 않습니다. CsUcsRollback를 실행 했지만: 진구 Myer의 사용자 서비스 정책은 변경 하지 않는 경우 어떻게 하나요? 이 경우: 진구의 연락처가 통합 된 연락처 저장소에서 일시적으로 제거 됩니다. 이 제거가 일시적인 것 이기는 데 유의 하세요. : 진구의 연락처가 통합 대화 상대 저장소에서 제거 된 후 비즈니스용 Skype 서버는 7 일이 지난 후: 진구에 할당 된 사용자 서비스 정책을 확인 합니다. : 진구에 통합 된 연락처 저장소의 사용자를 설정 하는 정책이 할당 되 면 해당 연락처가 연락처 저장소로 다시 자동으로 이동 됩니다. 통합 된 대화 상대 저장소에서 연락처를 영구적으로 제거 하려면 CsUcsRollback cmdlet을 실행 하는 것 외에 사용자 서비스 정책을 변경 해야 합니다.
  
마이그레이션에 영향을 줄 수 있는 많은 수의 변수 때문에 계정이 통합 된 연락처 저장소에 완전히 마이그레이션 되기까지 걸리는 시간을 예측 하기가 어렵습니다. 그러나 일반적으로 마이그레이션이 즉시 적용 되지는 않습니다. 적은 수의 대화 상대를 마이그레이션하는 경우에도 이동이 완료 되기 전에 10 분 이상 걸릴 수 있습니다.
  

