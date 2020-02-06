---
title: 비즈니스용 Skype 서버의 경험 치 설정 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: '요약: 비즈니스용 Skype 서버에서 체감 품질 데이터의 보존을 지정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a7f8173518d12daffb23658f5b81fa35b39d13da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817847"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 경험 치 설정 수정

**요약:** 비즈니스용 Skype 서버에서 체감 품질 데이터 보존을 지정 하는 방법에 대해 알아봅니다.

기본적으로 체감 품질 (환경 품질) 데이터는 60 일 후에 지워집니다. **경력 데이터** 페이지의 설정을 사용 하 여 오래 되거나 짧은 시간 동안 데이터를 유지할 수 있습니다. 체감 품질를 사용 하지 않도록 설정 하는 경우 체감 품질를 사용 하도록 설정 하기 전에 캡처한 데이터도 제거 될 수 있습니다.

> [!NOTE]
> 동일한 일 수 동안 데이터를 보존 하려면 체감 품질 (통화 정보 기록)를 구성 해야 합니다. 모니터링 보고서 홈페이지에서 사용할 수 있는 CDRs (통화 정보 보고서)의 각 통화는 CDR 및 체감 품질 정보를 포함 합니다. CDR 및 체감 품질의 제거 기간이 서로 다른 경우 일부 통화에는 CDR 데이터만 포함할 수 있고, 그 외에는 체감 품질 데이터만 포함 될 수 있습니다.

다음 절차에서는 체감 품질 데이터에 대 한 지우기 설정을 구성 하는 방법을 설명 합니다.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 체감 품질 데이터 보존을 지정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 **대리인 설정 사용**을 참조 하세요.

2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.

4. **경력 데이터** 페이지의 테이블에서 해당 사이트를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5. 제거를 설정 하려면 **체감 품질 제거 사용**을 선택 합니다.

6. **최대 기간 동안 체감 품질 유지 (일)** 체감 품질 데이터를 유지할 최대 일 수를 선택 합니다.

7. **커밋**을 클릭합니다.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 체감 품질 보존 지정

Windows PowerShell 및 **CsQoEConfiguration** cmdlet을 사용 하 여 체감 품질 보존 설정을 만들 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>특정 위치에 대 한 체감 품질 보존을 지정 하려면

- 이 명령을 사용 하 여 Redmond 사이트에 대 한 체감 품질 데이터를 제거 하 고, 사이트를 구성 하 여 20 일 동안 체감 품질 데이터를 유지 합니다.

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>여러 위치에 대 한 체감 품질 보존을 지정 하려면

- 이 명령은 조직에서 사용 중인 모든 체감 품질 구성 설정에 대해 체감 품질 보존을 구성 합니다.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

자세한 내용은 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.

## <a name="see-also"></a>참고 항목

[모니터링 배포](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
