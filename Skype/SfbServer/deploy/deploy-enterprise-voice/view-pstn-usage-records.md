---
title: PSTN 사용 레코드 보기 비즈니스용 Skype
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: '요약: 비즈니스용 Skype 서버 관리 셸을 사용하여 PSTN 사용 레코드를 비즈니스용 Skype 서버 방법을 설명하는 방법을 제공합니다.'
---

# <a name="view-pstn-usage-records-in-skype-for-business"></a>PSTN 사용 레코드 보기 비즈니스용 Skype

**요약:** 비즈니스용 Skype 서버 관리 셸을 사용하여 PSTN 사용 레코드를 보는 비즈니스용 Skype 서버 대해 자세히 알아보습니다.

PSTN(Public Switched Telephone Network) 사용 레코드는 조직의 여러 사용자 또는 사용자 그룹이 만들 수 있는 통화 클래스(예: 내부, 로컬 또는 시거리)를 지정합니다. 자세한 내용은 계획 설명서에서 [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records)를 참조하십시오.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 PSTN 사용 레코드를 비즈니스용 Skype 서버

1. 제어판을 비즈니스용 Skype 서버 를 니다.

2. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭하고 **PSTN 사용** 을 클릭합니다.

3. **PSTN 사용** 페이지에서 보려는 PSTN 사용 레코드를 강조 표시하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.

    > [!NOTE]
    > 선택한 PSTN 사용 레코드의 읽기 전용 페이지에 연결된 경로 및 음성 정책이 표시됩니다.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>관리 셸 cmdlet을 사용하여 PSTN 비즈니스용 Skype 서버 확인

- 모든 PSTN 사용에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 후 Enter를 누르고 있습니다.

  ```powershell
  Get-CsPstnUsage
  ```

    이 명령은 다음과 비슷한 정보를 반환합니다.

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>참고 항목

[음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 비즈니스용 Skype](voice-policy-and-pstn-usage-records.md)