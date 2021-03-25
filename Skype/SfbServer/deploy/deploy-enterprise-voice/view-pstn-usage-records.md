---
title: 비즈니스용 Skype에서 PSTN 사용 레코드 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: '요약: 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 PSTN 사용 레코드를 보는 방법을 설명하는 방법을 제공합니다.'
ms.openlocfilehash: 6a447f7aeb9db0a7ca858cf58df10273c28b533b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109834"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>비즈니스용 Skype에서 PSTN 사용 레코드 보기

**요약:** 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 PSTN 사용 레코드를 보는 방법을 학습합니다.

PSTN(Public Switched Telephone Network) 사용 레코드는 조직의 여러 사용자 또는 사용자 그룹이 만들 수 있는 통화 클래스(예: 내부, 로컬 또는 시거리)를 지정합니다. 자세한 내용은 계획 설명서에서 [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records)를 참조하십시오.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 PSTN 사용 레코드를 확인

1. 비즈니스용 Skype 서버 제어판을 니다.

2. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭하고 **PSTN 사용** 을 클릭합니다.

3. **PSTN 사용** 페이지에서 보려는 PSTN 사용 레코드를 강조 표시하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.

    > [!NOTE]
    > 선택한 PSTN 사용 레코드의 읽기 전용 페이지에 연결된 경로 및 음성 정책이 표시됩니다.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하여 PSTN 사용 정보를 확인

- 모든 PSTN 사용에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력한 다음 Enter를 누르고 있습니다.

  ```powershell
  Get-CsPstnUsage
  ```

    이 명령은 다음과 비슷한 정보를 반환합니다.

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>참고 항목

[음성 정책 만들기 또는 수정 및 비즈니스용 Skype에서 PSTN 사용 레코드 구성](voice-policy-and-pstn-usage-records.md)