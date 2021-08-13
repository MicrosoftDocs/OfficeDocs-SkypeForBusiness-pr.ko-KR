---
title: 통화 정보 기록을 사용하도록 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: '요약: CDR(통화 정보 기록) 레코드를 사용하도록 설정하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 1d09e637d75b9617abf669f75e96076333380a075010bd3d641f4c5189be9d89
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301384"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>통화 정보 기록을 사용하도록 비즈니스용 Skype 서버

**요약:** CDR(통화 정보 기록) 레코드를 사용하도록 설정하는 방법을 비즈니스용 Skype 서버.

CDR(통화 정보 기록)은 인스턴트 메시징, VoIP(Voice over Internet Protocol) 통화, 응용 프로그램 공유, 파일 전송, 모임 등의 피어 투 피어 활동에 대한 사용 및 진단 정보를 기록합니다. 이러한 사용 데이터는 ROI(투자 수익률)를 계산하는 데 사용하고, 진단 데이터는 피어-투-피어 활동 및 모임 관련 문제를 해결하는 데 사용할 수 있습니다.

다음 절차에 따라 조직의 각 사이트 또는 조직 전체에 대해 CDR을 사용하도록 설정합니다.

> [!NOTE]
> CDR을 사용하도록 설정하려면 먼저 모니터링 및 모니터링 데이터베이스를 구성해야 합니다. 자세한 내용은 [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)를 참조하십시오.

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>제어판에서 CDR을 비즈니스용 Skype 서버

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **통화 정보 기록** 을 클릭합니다.

4. **통화 정보 기록** 페이지의 표에서 적절한 사이트를 클릭하고 **동작** 을 클릭한 후에 **CDR 사용** 을 클릭합니다.

    > [!NOTE]
    > CDR은 기본적으로 사용하도록 설정됩니다.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 CDR Windows PowerShell 설정

**SET-CsCdrConfiguration** cmdlet과 Windows PowerShell CDR을 사용하도록 설정할 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 서버를 사용하여 Windows PowerShell 연결하는 비즈니스용 Skype 서버 ["빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)블로그 문서를 참조하십시오. 프로세스는 동일한 비즈니스용 Skype 서버.

### <a name="to-enable-cdr-for-a-single-location"></a>단일 위치에 대해 CDR을 사용하도록 설정하려면

 CDR을 사용하도록 설정하려면 EnableCDR 매개 변수를 True($True)로 설정합니다.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>단일 위치에 대해 CDR을 사용하지 않도록 설정하려면

 CDR을 사용하지 않도록 설정하려면 EnableCDR 매개 변수를 False($False)로 설정합니다. CDR을 사용 안 하게 해서 모니터링이 제거되지는 않습니다. CDR 데이터 수집 및 저장을 일시 중지합니다.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>단일 명령을 사용하여 여러 위치에서 CDR을 사용하도록 설정하려면

 다음 명령은 조직에서 현재 사용 중인 모든 CDR 구성 설정에 대해 CDR을 사용하도록 설정합니다.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

자세한 내용은 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="see-also"></a>참고 항목

[모니터링 계획](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[모니터링 배포](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)