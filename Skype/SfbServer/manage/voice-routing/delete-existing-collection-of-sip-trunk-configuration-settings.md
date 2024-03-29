---
title: 비즈니스용 Skype 서버 - SIP 트렁크 구성 설정의 기존 컬렉션 삭제
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: SIP 트렁크 구성 설정은 중재 서버와 공용 전화망 게이트웨이, IP-공용 분기 교환 또는 서비스 공급자의 세션 경계 컨트롤러 간의 관계와 기능을 정의합니다.
ms.openlocfilehash: 974ace39449314ab29c9f058a64ee214f833fab3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395200"
---
# <a name="skype-for-business-server---delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>비즈니스용 Skype 서버 - SIP 트렁크 구성 설정의 기존 컬렉션 삭제

SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.

- 트렁크에 미디어 우회를 설정할지 여부
- RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건
- SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부

설치 비즈니스용 Skype 서버 SIP 트렁크 구성 설정의 전역 컬렉션이 만들어집니다. 이 전역 설정 컬렉션은 삭제할 수 없습니다. 그러나 비즈니스용 Skype ServerControl Panel 또는 [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet을 사용하여 전역 컬렉션의 속성을 기본값으로 "다시 설정"할 수 있습니다. 예를 들어 Enable3pccRefer 속성을 True로 설정한 경우 전역 컬렉션을 다시 설정하면 Enable3pccRefer 속성이 기본값인 False로 돌아갑니다.

관리자는 개별 PSTN 게이트웨이에 대해 사이트 범위 또는 서비스 범위에서 사용자 지정 트렁크 구성 설정을 만들 수도 있습니다. 이러한 사용자 지정 설정은 제거할 수 있습니다. 이와 같은 사용자 지정 설정을 제거할 때는 다음 사항에 유의하십시오.

- 서비스 범위 설정을 제거하면 해당 설정에 의해 관리되는 SIP 트렁크는 사이트에 적용되는 설정(있는 경우)에 의해 관리됩니다. 사이트 설정이 없으면 트렁크는 트렁크 구성 설정의 전역 컬렉션에 의해 관리됩니다.
- 사이트 범위 설정을 제거하면 해당 설정에 의해 관리되는 SIP 트렁크는 트렁크 구성 설정의 전역 컬렉션에 의해 관리됩니다.

**제어판을 사용하여 트렁크 구성 비즈니스용 Skype 서버 제거하려면** 

1. 비즈니스용 Skype 서버 제어판에서 음성 라우팅을 **클릭** 한 다음 트렁 **크 구성을 클릭합니다**.
2. 트렁 **크 구성 탭** 에서 삭제할 SIP 트렁크 구성 설정 컬렉션을 선택하고 **편집을 클릭** 한 다음 삭제를 **클릭합니다**. 같은 작업에서 여러 컬렉션을 삭제하려면 삭제할 첫 번째 컬렉션을 클릭하고 Ctrl 키를 누른 상태로 제거할 추가 컬렉션을 클릭합니다.
3. 컬렉션의 **상태** 속성은 **커밋되지 않음** 으로 업데이트됩니다. 변경 내용을 커밋하고 컬렉션을 삭제하려면 **커밋** 을 클릭한 후 **모두 커밋** 을 클릭합니다.
4. **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인** 을 클릭합니다.
5. 제어 **판 비즈니스용 Skype 서버 대화** 상자에서 확인을 **클릭합니다**.
6. 마음이 바뀌어 컬렉션을 삭제하지 않을 경우 커밋을 클릭한 다음 커밋되지 않은 모든 변경 내용 취소 **를 클릭합니다**. 제어 **판 비즈니스용 Skype 서버 상자** 가 나타나면 확인을 **클릭합니다**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 트렁크 구성 Windows PowerShell 제거


트렁크 구성 설정은 **Remove-CsTrunkConfiguration** cmdlet과 Windows PowerShell 삭제할 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 

**지정한 설정 컬렉션을 제거하려면**

다음 명령은 Redmond 사이트에 적용된 트렁크 구성 설정을 제거합니다.

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**사이트 범위에 적용된 모든 컬렉션을 제거하려면**

다음 명령은 서비스 범위에 적용된 모든 트렁크 구성 설정을 제거합니다.

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**미디어 우회가 사용하도록 설정된 모든 컬렉션을 제거하려면**

다음 명령은 미디어 바이패스가 사용하도록 설정된 모든 트렁크 구성 설정을 제거합니다.

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

자세한 내용은 [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet에 대한 도움말 항목을 참조하십시오.
