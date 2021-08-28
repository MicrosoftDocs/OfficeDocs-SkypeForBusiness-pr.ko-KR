---
title: 재해 복구 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 비즈니스용 Skype 서버 풀 서버에 대해 시스템 복구를 수행하여 문서화한 재해 복구 프로세스를 테스트합니다.
ms.openlocfilehash: a98f2de4d860c4a769526428958ba9b952cfc573
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609245"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>재해 복구 비즈니스용 Skype 서버

비즈니스용 Skype 서버 풀 서버에 대해 시스템 복구를 수행하여 문서화한 재해 복구 프로세스를 테스트합니다. 이 테스트는 한 서버에 대한 전체 하드웨어 실패를 시뮬레이트하며, 리소스, 계획 및 데이터를 복구에 사용할 수 있도록 보장하는 데 도움이 됩니다. 조직에서 매월 다른 서버 또는 다른 장비의 실패를 테스트할 수 있도록 매월 테스트의 포커스를 회전해 보아야 합니다. 

조직에서 재해 복구 테스트를 수행하는 일정은 달라집니다. 재해 복구 테스트는 무시되거나 무시되지 않는 것이 매우 중요합니다. 

토폴로지비즈니스용 Skype 서버 및 구성 설정을 파일로 내보낼 수 있습니다. 이 파일을 사용하여 업그레이드, 하드웨어 오류 또는 기타 문제로 인해 데이터가 손실된 후 이 정보를 중앙 관리 저장소로 복원할 수 있습니다.

다음 비즈니스용 Skype 서버 같이 토폴로지, 정책 및 구성 설정을 중앙 관리 저장소 또는 로컬 컴퓨터로 가져올 수 있습니다. 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

프로덕션 데이터를 백업하는 경우:

- 표준 SQL Server 백업 프로세스를 사용하여 RTC 및 LCSLog 데이터베이스를 백업하여 파일 또는 테이프 덤프 장치에 데이터베이스를 덤프합니다.
- 타사 백업 응용 프로그램을 사용하여 데이터를 파일 또는 테이프에 백업합니다.
- Export-CsUserData cmdlet을 사용하여 전체 RTC 데이터베이스의 XML 내보내기 기능을 만듭니다.
- 파일 시스템 백업 또는 타사 백업을 사용하여 모임 콘텐츠 및 준수 로그를 백업합니다.
- 명령줄 Export-CsConfiguration 사용하여 비즈니스용 Skype 서버 백업합니다.

장애 조치(failover) 절차의 첫 번째 단계에서는 사용자를 프로덕션 풀에서 재해 복구 풀로 강제 이동하는 과정을 포함합니다. 프로덕션 풀은 사용자 재배치에 동의할 수 없는 강제 이동입니다.

사용자 비즈니스용 Skype 서버 이동 프로세스는 RTC 데이터베이스의 레코드 업데이트뿐만 아니라 사용자 계정 개체의 특성도 효과적으로 SQL 있습니다. 이 데이터는 표준 SQL Server 복원 프로세스 또는 타사 백업/복원 유틸리티를 SQL Server 원래 백업 SQL Server 덤프 장치에서 복원할 수 있습니다.

이 데이터를 복원한 후 사용자는 재해 복구 풀에 효과적으로 연결하고 평소처럼 작동할 수 있습니다. 사용자가 재해 복구 풀에 연결할 수 있도록 설정하려면 DNS 레코드 변경이 필요합니다.

프로덕션 비즈니스용 Skype 풀은 다음의 자동 구성 및 DNS SRV 레코드를 사용하여 클라이언트에서 참조됩니다.

- SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain>
- CNAME: SIP.\<domain> /cvc-pool-1.\<domain>

장애 조치(failover)를 용이하게 하기 위해 DROCSPool FQDN을 참조하도록 이 CNAME 레코드를 업데이트해야 합니다.

- CNAME: SIP.<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- AV.\<domain>
- webconf.\<domain>
