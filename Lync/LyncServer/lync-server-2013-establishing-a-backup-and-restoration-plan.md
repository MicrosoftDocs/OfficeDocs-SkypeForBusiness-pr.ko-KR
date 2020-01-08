---
title: 'Lync Server 2013: 백업 및 복원 계획 수립'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b3516e63a7cbada4a89fad3540406e38b299fef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Lync Server 2013의 백업 및 복원 계획 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-17_

백업 및 복원 계획을 만들려면 다음과 같은 단계가 필요 합니다.

  - 계획 개발.

  - 계획 구현.

  - 계획을 유지 관리 합니다.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>백업 및 복원 계획 개발

Lync Server에 대 한 백업 및 복원 전략을 개발한 후에는이를 사용 하 여 자세한 백업 및 복원 계획을 문서화 합니다. 데이터 및 설정 백업에 대 한 우선 순위와 요구 사항을 명확 하 게 전달 하는 계획을 세워야 합니다. [Lync server 2013의 백업 및 복원 전략 설정](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) 및 [lync Server 2013 용 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md) 의 워크시트에 대 한 정보를 사용 하 여 전략 설명서를 쉽게 활용할 수 있습니다. 계획에는 서비스 복원 시기 및 방법을 결정 하는 조건도 포함 해야 합니다.

계획을 개발할 때 다음을 고려 하 고 계정을 고려해 야 합니다.

  - 새 하드웨어에서 서버를 복구 하는 방법

  - 여러 비즈니스 영역이 나 부서의 작업을 수행 해야 하는 서비스를 복구 하는 방법

  - 여분 서버를 신속 하 게 구입 하는 방법.

  - 전략을 사용 하 여 복구 하는 데 걸리는 시간입니다. 조직의 RTO (복구 시간 목적)에 대 한 요구 사항을 고려 합니다.

배포의 서버와 구성 요소를 반영 하기 위해 적절 하 게 프로시저를 추가 하 고 삭제 하 여이 항목의 백업 및 복원 절차를 수정 합니다. 또한 백업 일정과 같은 적절 한 세부 정보를 적절 한 절차에 추가 하 여 정보가 간과 되지 않도록 할 수 있습니다.

<div>


> [!NOTE]  
> 프로시저의 품질과 reproducibility을 확인 하는 데 도움이 되도록 최대한 많은 단계를 위해 스크립트를 만드는 것이 좋습니다.



</div>

계획에서 계획을 검토할 책임이 있는 사용자, 새 프로시저 또는 도구를 테스트 하 고 유효성을 검사 하는 사용자, 계획 및 관련 절차에 대 한 변경 내용을 승인 해야 하는 사람을 지정 합니다.

백업 및 복원 계획이 설정 된 모든 목표 및 우선 순위를 완전히 충족 하는지 확인 하려면 계획을 구현 하기 전에 조직의 적절 한 비즈니스 의사 결정권자 및 기술 의사 결정권자에 대 한 승인을 받아야 합니다.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>백업 및 복원 계획 구현

백업 및 복원 계획을 구현 하려면 다음 단계가 필요 합니다.

  - 계획 테스트 및 유효성 검사

  - 계획을 전달 합니다.

  - 백업 및 복원 작업의 유효성을 검사 합니다.

<div>

## <a name="testing-and-validating-the-plan"></a>계획 테스트 및 유효성 검사

랩 환경에서 여기에 설명 된 절차를 테스트 하 고 유효성을 검사 했습니다. 이러한 절차 또는 다른 절차가 해당 환경에서 작동 하는지 확인 하려면 구현 하려는 각 프로시저를 테스트 하 고 유효성을 검사 해야 합니다. 최종 승인에 대 한 계획을 제출 하기 전에 테스트 및 유효성 검사를 완료 합니다.

</div>

<div>

## <a name="communicating-the-plan"></a>계획 통신

백업 및 복원 계획에서는 프로시저를 수행 하기 위한 절차와 단계별 지침을 구현 하는 사용자를 명확 하 게 설명 해야 합니다. 백업 및 복원의 모든 측면을 담당 하는 모든 사용자가 계획, 구현 방법, 역할에 대해 잘 알고 있어야 합니다. 여기에는 다음에 대 한 구현 요구 사항이 모두 포함 됩니다.

  - 풀 및 서버 백업

  - 서비스 복원.

**풀 및 서버 백업**

백업 및 복원 계획에는 지속적으로 백업 절차를 완료 하는 데 필요한 모든 정보가 포함 되어야 합니다. 책임자 팀 구성원에 게 전달 되는 주요 정보에는 다음이 포함 됩니다.

  - 각 서버 백업을 담당 하는 팀 또는 사용자 (개인 또는 역할로 지정 됨)

  - 각 서버를 백업 하기 위한 특정 일정

  - 각 데이터 형식 (설정, 데이터베이스, 파일 공유)에 대 한 백업 위치

  - 각 절차를 완료 하는 데 필요한 도구를 포함 하 여 사용할 백업 절차

  - [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 명시 된 대로 백업을 완료 하는 데 필요한 정보

  - 정기적 감사 및 테스트 복원을 포함할 수 있는 데이터 및 설정이 적절 하 게 백업 되 고 복원 가능한 지 확인 하는 데 사용 되는 유효성 검사 메서드.

**서비스 복원**

하나 이상의 서버에서 서비스를 사용할 수 없게 되는 손실이 발생 하는 경우 백업 및 복원 계획에 서비스를 복원 하는 데 필요한 모든 정보가 포함 되어야 합니다. 책임자 팀 구성원에 게 전달 되는 주요 정보에는 다음이 포함 됩니다.

  - 서비스 복원이 필요한 시기와 서비스를 복원 하는 데 사용 되는 절차 및 각 사용자에 대 한 절차를 구현 해야 하는 팀 또는 사용자를 결정 하는 팀 또는 개인 (개인 또는 역할로 지정 됨) 복원 시나리오.

  - 특정 상황에 가장 적합 한 복원 절차를 결정 하는 조건입니다.

  - 각 복원 시나리오에서 서비스 및 RTO (복구 시간 목표) 복원에 대 한 시간을 예측 합니다.

  - 각 절차를 완료 하는 데 필요한 도구를 포함 하 여 복원 절차를 사용할 수 있습니다.

  - 데이터 및 설정을 복원 하는 데 필요한 정보입니다. 워크시트는 [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 제공 됩니다.

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>백업 및 복원 작업의 유효성 검사

실제 환경에서 초기 백업 노력을 완료 한 후 지정 된 간격 (백업 및 복원 계획에 명시 된 대로)에서 다음 사항을 확인 해야 합니다.

  - 필요에 따라 백업이 진행 됩니다.

  - 백업 된 데이터 및 설정에 액세스할 수 있습니다.

  - 복원 절차는 백업 및 복원 계획에 지정 된 RTO (복구 시간 목표) 시간 내에 수행할 수 있으며, 결과는 모든 비즈니스 요구 사항에 맞습니다.

  - 백업 워크시트를 완료 하 고 확인 한 후 안전한 위치에 저장 합니다. 이러한 워크시트는 [Lync Server 2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 제공 됩니다.

  - 백업 및 복원 계획에 지정 된 대로 복원 절차가 테스트 되 고 예상 대로 작동 하는지 확인 되었습니다.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>백업 및 복원 계획 유지 관리

Lync 서버 토폴로지는 조직과 달라 지는 동적 환경입니다. 조직의 변화에 따라 백업 및 복원 계획을 Reassess 하 고 정기적으로 검토 하 여 비즈니스 요구에 맞게 지속적으로 진행 되도록 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

