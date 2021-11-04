---
title: 2013에서 모니터링 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: '요약: 모니터링을 배포하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: cbb5fe0974e1b02ce5be472ba91d01221fb7df82
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764846"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>2013에서 모니터링 비즈니스용 Skype 서버

**요약:** 모니터링을 배포하는 방법을 비즈니스용 Skype 서버.

이러한 작업을 수행하기 전에 에서 모니터링 계획을 [비즈니스용 Skype 서버.](../../plan-your-deployment/monitoring.md)

일반적으로 다음 두 단계를 완료하여 토폴로지 내에서 모니터링 서비스를 구현합니다.

1. 새 풀을 설정하는 동시에 모니터링을 비즈니스용 Skype 서버. 이 비즈니스용 Skype 서버 풀 기준에 따라 모니터링이 사용 또는 사용되지 않도록 설정됩니다. 이 설명서의 통화 정보 기록 및 경험 품질 구성 섹션에 설명된 프로세스인 모니터링 데이터를 실제로 수집하지 않고도 풀에 대한 모니터링을 사용하도록 설정할 설정 있습니다.

2. 모니터링 저장소(모니터링 데이터베이스)를 새 풀과 연결합니다. 단일 모니터링 저장소를 여러 풀과 연결할 수 있습니다. 즉, 등록자 풀에 있는 사용자의 수에 따라서는 각 풀에 대해 별도의 모니터링 데이터베이스를 설정하지 않아도 됩니다. 대신 단일 모니터링 저장소를 여러 풀에서 사용할 수 있습니다.

새 풀을 만들 때 모니터링을 사용하도록 설정하는 것이 더 쉬운 경우가 쉽지만 모니터링을 사용하지 않도록 설정한 새 풀을 만들 수도 있습니다. 이렇게 하면 나중에 토폴로지 작성기에서 서비스를 사용하도록 설정할 수 있습니다. 토폴로지 작성기에서는 풀에 대한 모니터링을 활성화 또는 비활성화하거나 풀을 다른 모니터링 저장소와 연결하기 위한 방법을 제공합니다. 더 이상 모니터링 서버 역할이 없는 경우에도 모니터링 서비스에서 수집한 데이터를 저장하는 데 사용되는 백 엔드 데이터베이스인 모니터링 저장소를 하나 이상 만들어야 합니다. 이러한 백 엔드 데이터베이스는 Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 또는 Microsoft SQL Server 2019를 사용하여 만들 수 있습니다.

> [!NOTE]
> 풀에 대해 모니터링을 사용하도록 설정한 경우 토폴로지 변경 없이 모니터링 데이터를 수집하는 프로세스를 사용하지 않도록 설정할 수 있습니다. 비즈니스용 Skype 서버 CDR(통화 정보 기록) 또는 QoE(QoE) 데이터 수집을 사용하지 않도록 설정하고 나중에 다시 사용하도록 설정할 수 있습니다. 자세한 내용은 이 문서의 통화 정보 기록 및 품질 설정 섹션을 참조하십시오.

비즈니스용 Skype 서버 모니터링 기능의 또 다른 중요한 기능 중 하나는 비즈니스용 Skype 서버 모니터링 보고서가 IPv6을 지원하고 있습니다. IP 주소 필드를 사용하는 보고서에는 사용되는 SQL 쿼리에 따라 IPv4 또는 IPv6 주소가 표시됩니다. 및, 2) IPv6 주소가 모니터링 데이터베이스에 저장되어 있는 경우

> [!NOTE]
> SQL Server 에이전트 서비스 시작 유형이 자동으로 실행되고 SQL Server 에이전트 서비스가 모니터링 데이터베이스를 보유하는 SQL 인스턴스에 대해 실행 중인지 확인하여 기본 모니터링 SQL Server 유지 관리 작업이 SQL Server 에이전트 서비스의 제어에 따라 예약된 기준으로 실행될 수 있도록 합니다.

이 설명서에서는 사용자에 대한 모니터링 및 모니터링 보고서를 설치하고 구성하는 프로세스를 비즈니스용 Skype 서버. 또한 다음 작업을 수행할 수 있도록 단계별 지침을 제공합니다.

- 토폴로지에서 모니터링을 사용하도록 설정하고 프런트 엔드 풀과 모니터링 저장소를 연결합니다.

- 모니터링 SQL Server Reporting Services 비즈니스용 Skype 서버 설치합니다. 모니터링 보고서는 모니터링 데이터베이스에 저장된 정보에 대한 여러 가지 보기를 제공하는 미리 구성된 보고서입니다.

- CDR(통화 정보 기록) 및 QoE(QoE) 데이터 수집을 구성합니다. 통화 정보 기록을 사용하면 VoIP(Voice over IP) 전화 통화와 같은 비즈니스용 Skype 서버 기능의 사용을 추적할 수 있습니다. IM(인스턴트 메시징) 파일 전송 A/V(오디오/비디오) 회의 및 응용 프로그램 공유 세션. QoE 메트릭은 손실된 네트워크 패킷 수, 백그라운드 노이즈, "지터"(패킷 지연의 차이) 크기 등 조직의 오디오 및 비디오 통화 품질을 추적합니다.

- 모니터링 데이터베이스에서 CDR 및/또는 QoE 레코드를 수동으로 삭제합니다.

## <a name="deployment-checklist-for-monitoring"></a>모니터링을 위한 배포 검사 목록

각 프런트 엔드 서버에 모니터링이 이미 설치 및 활성화되어 있는 경우도 여전히 몇 가지 단계를 수행한 후 해당 서버에 대한 모니터링 데이터를 실제로 수집할 비즈니스용 Skype 서버. 이러한 단계는 다음 검사 목록에 설명되어 있습니다.

|**작업 단계**|**단계**|**역할 및 그룹 구성원 자격**|**설명서**|
|:-----|:-----|:-----|:-----|
|**하드웨어 및 소프트웨어 필수 구성 요소 설치** <br/> |모니터링을 위한 백 엔드 데이터 저장소로 작동할 컴퓨터에 지원되는 버전의 Microsoft SQL Server를 설치합니다.  <br/> |로컬 관리자 그룹의 구성원인 도메인 사용자여야 합니다.  <br/> |[지원되는 하드웨어](/previous-versions/office/lync-server-2013/lync-server-2013-supported-hardware) <br/> [서버 소프트웨어 및 인프라 지원](/previous-versions/office/lync-server-2013/lync-server-2013-server-software-and-infrastructure-support) <br/> |
|**모니터링을 지원하는 적절한 내부 토폴로지 만들기** <br/> |토폴로지 비즈니스용 Skype 서버 사용하여 모니터링 데이터베이스를 토폴로지에 추가한 다음 업데이트된 토폴로지 게시  <br/> |토폴로지를 정의하려면 로컬 사용자 그룹의 구성원인 사용자여야 합니다.  <br/> 토폴로지를 게시하려면 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원이어야 합니다.  <br/> |[모니터링 저장소를 모니터링 저장소의 프런트 엔드 풀과 비즈니스용 Skype 서버](associate-a-monitoring-store.md) <br/> |
|**적합한 모니터링 설정 사용** <br/> |전역 및/또는 사이트 범위에서 CDR(통화 정보 기록) 및/또는 QoE(QoE) 모니터링을 사용하도록 설정할 수 있습니다.  <br/> |RTCUniversalServerAdmins 그룹의 구성원인 사용자 또는 CsCdrConfiguration 및 CsQoEConfiguration cmdlet에 대한 액세스 권한을 제공하는 RBAC 역할이 지정된 사용자여야 합니다.  <br/> |[통화 정보 기록 및 품질 설정을 비즈니스용 Skype 서버](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>모니터링 사용

통합 데이터 수집 에이전트가 각 프런트 엔드 서버에 자동으로 설치 및 활성화되어도, 통합 데이터 수집 에이전트 설치를 완료하는 순간 모니터링 데이터 수집이 자동으로 시작되는 것은 비즈니스용 Skype 서버. 대신 프런트 엔드 서버/프런트 엔드 풀을 모니터링 데이터베이스에 연결하고 전역 범위 및/또는 사이트 범위에서 CDR(통화 정보 기록) 및/또는 QoE(QoE) 모니터링을 사용하도록 설정해야 합니다.

프런트 엔드 서버 또는 프런트 엔드 풀을 모니터링 데이터베이스와 연결하기 위한 단계별 지침은 배포 가이드에서 [Associate a monitoring store with a Front End pool in 비즈니스용 Skype 서버](associate-a-monitoring-store.md) 항목을 참조하십시오. 이러한 연결 및 새 비즈니스용 Skype 서버 토폴로지가 게시된 후에도 모니터링 데이터를 수집할 수 없습니다. 이는 CDR 및 QoE 데이터 수집을 모두 설치하면 기본적으로 사용하지 않도록 설정되어 있기 비즈니스용 Skype 서버.

데이터 수집을 시작하려면 CDR 및/또는 QoE 모니터링을 사용하도록 설정해야 합니다. CDR 및 QoE 모니터링을 모두 사용하도록 설정할 것은 없습니다. 원하는 경우 다른 유형의 모니터링을 사용하지 않도록 설정한 채 한 가지 유형의 모니터링을 사용하도록 설정할 수 있습니다. 전역 범위에서 CDR 모니터링을 사용하도록 설정하려면 전역 관리 셸 내에서 비즈니스용 Skype 서버 실행합니다.

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

또는 제어판 내에서 CDR 모니터링을 사용하도록 설정할 비즈니스용 Skype 서버 있습니다. 비즈니스용 Skype 서버 제어판 내에서 다음 절차를 완료합니다.

1. **모니터링** 을 클릭합니다.

2. 통화 정보 **기록** 탭에서 전역 설정을 **두 번** 클릭합니다.

3. **CDR(통화 정보 기록)** 설정 편집 창에서 **CDR** 모니터링 사용 을 선택한 다음 커밋을 **클릭합니다.**

전역 범위에서 QoE 모니터링을 사용하도록 설정하려면 전역 관리 셸 내에서 비즈니스용 Skype 서버 실행합니다.

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

원하는 경우 비즈니스용 Skype 서버 제어판 내에서 QoE 모니터링을 사용하도록 설정할 수 있습니다. 제어판 내에서 다음 절차를 완료합니다.

1. **모니터링** 을 클릭합니다.

2. 경험 **품질** 데이터 탭에서 전역 설정을 **두 번** 클릭합니다.

3. **QoE(QoE)** 설정 편집 창에서 **QoE** 데이터 모니터링 사용 을 선택한 다음 **커밋을 클릭합니다.**

앞의 예제에서는 전역 범위에서 모니터링을 사용하도록 설정한 경우 즉, 조직 전체에서 CDR 및 QoE 모니터링을 사용하도록 설정할 수 있습니다. 또는 사이트 범위에서 별도의 CDR 및 QoE 구성 설정을 만든 다음 각 사이트에 대해 모니터링을 선택적으로 설정하거나 사용하지 않도록 설정할 수 있습니다. 예를 들어 Redmond 사이트에 대해 CDR 모니터링을 사용하도록 설정하고 Dublin 사이트에 대해 CDR 모니터링을 사용하지 않도록 설정할 수 있습니다. 모니터링 구성 설정 관리에 대한 자세한 내용은 배포 가이드 항목 에서 통화 정보 기록 및 품질 설정 [구성을 비즈니스용 Skype 서버.](call-detail-recording-and-qoe.md)

## <a name="see-also"></a>참고 항목

[2013의 모니터링 비즈니스용 Skype 서버](../../plan-your-deployment/monitoring.md)