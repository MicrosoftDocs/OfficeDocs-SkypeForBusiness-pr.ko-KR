---
title: 사용자 환경의 경험 품질 설정 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: '요약: QoE 데이터의 보존을 지정하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 38bc88866e4bd8b677873b2d502e9268305ccf49
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770246"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>사용자 환경의 경험 품질 설정 비즈니스용 Skype 서버

**요약:** QoE 데이터의 보존을 지정하는 방법을 비즈니스용 Skype 서버.

QoE(체감 품질) 데이터는 기본적으로 60일 후에 삭제됩니다. **체감 품질 데이터** 페이지의 설정을 사용하여 데이터를 60일 이상 보존하거나 60일보다 짧게 보존할 수 있습니다. QoE를 사용하지 않도록 설정한 경우 QoE를 사용하도록 설정하기 전에 캡처한 데이터도 삭제됩니다.

> [!NOTE]
> CDR(통화 정보 기록) 및 QoE의 데이터 보존 일수는 동일하게 구성해야 합니다. 모니터링 보고서 홈 페이지에 제공되는 CDR(통화 정보 보고서)의 각 통화에는 CDR 및 QoE 정보가 포함됩니다. CDR 및 QoE의 삭제 기간이 다를 경우 일부 통화에는 CDR 데이터만 포함되고 또 다른 일부 통화에는 QoE 데이터만 포함될 수 있습니다.

다음 절차는 QoE 데이터에 대한 삭제 설정을 구성하는 방법을 설명합니다.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 QoE 데이터의 보존을 비즈니스용 Skype 서버

1.  RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **체감 품질 데이터** 를 클릭합니다.

4. **체감 품질 데이터** 페이지의 테이블에서 적합한 사이트를 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.

5. 삭제를 설정하려면 **QoE 삭제 사용** 을 선택합니다.

6. **최대 기간(일) 동안 QoE 유지** 에서 QoE 데이터를 보존할 최대 일수를 선택합니다.

7. **커밋** 을 클릭합니다.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Cmdlet을 사용하여 QoE 보존 Windows PowerShell 지정

**Set-CsQoEConfiguration** cmdlet과 Windows PowerShell 사용하여 QoE 보존 설정을 만들 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>특정 위치에 대한 QoE 보존을 지정하려면

- 이 명령은 Redmond 사이트에 대해 QoE 데이터 삭제를 사용하도록 설정하고 20일 동안 QoE 데이터를 유지하도록 구성합니다.

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>여러 위치에 대한 QoE 보존을 지정하려면

- 이 명령은 조직에서 사용 중인 모든 QoE 구성 설정에 대해 QoE 보존을 구성합니다.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

자세한 내용은 [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="see-also"></a>참고 항목

[모니터링 배포](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)