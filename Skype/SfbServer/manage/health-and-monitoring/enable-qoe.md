---
title: 사용자 환경의 경험 품질 비즈니스용 Skype 서버
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
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '요약: QoE(QoE)를 사용하도록 설정하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: aa1f755dbc19da959f54f6af882bff2049363d6f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767706"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>사용자 환경의 경험 품질 비즈니스용 Skype 서버

**요약:** QoE(QoE)를 사용하도록 설정하는 방법을 비즈니스용 Skype 서버.

QoE(체감 품질)는 통화 및 세션에 포함된 참가자, 장치 이름, 드라이버, IP 주소, 끝점 유형에 대한 정보 및 미디어의 품질을 나타내는 숫자 데이터를 기록합니다. 자세한 내용은 계획 설명서에서 [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)을 참조하십시오.

다음 절차를 사용하여 전체 조직이나 조직의 각 사이트에 대해 QoE를 사용하도록 설정할 수 있습니다.

> [!NOTE]
> QoE를 사용하도록 설정하려면 먼저 모니터링 및 모니터링 백 엔드 데이터베이스를 구성해야 합니다. 자세한 내용은 [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)를 참조하십시오.

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 QoE를 비즈니스용 Skype 서버

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **체감 품질 데이터** 를 클릭합니다.

4. **체감 품질 데이터** 페이지의 테이블에서 적합한 컬렉션을 클릭하고 **동작**, **QoE 사용** 을 차례로 클릭합니다.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Cmdlet을 사용하여 QoE Windows PowerShell 사용

**Set-CsQoEConfiguration** cmdlet과 set-Windows PowerShell 사용하여 QoE를 사용하도록 설정할 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.

### <a name="to-enable-qoe-for-a-single-location"></a>단일 위치에서 QoE를 사용하도록 설정하려면

 QoE를 사용하도록 설정하려면 EnableQoE 매개 변수를 True($True)로 설정합니다.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>단일 위치에서 QoE를 사용하지 않도록 설정하려면

 QoE를 사용하지 않도록 설정하려면 EnableQoE 매개 변수를 False($False)로 설정합니다. 이 경우 모니터링이 제거되지는 않습니다. 다만 컬렉션과 QoE 데이터 저장소가 일시 중지됩니다.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>단일 명령을 사용하여 여러 위치에서 QoE를 사용하도록 설정하려면

 다음 명령을 사용하면 조직에서 현재 사용 중인 모든 QoE 구성 설정에 대해 QoE를 사용하도록 설정할 수 있습니다.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

자세한 내용은 [Set-CsQoEConfiguration을 참조합니다.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>참고 항목

[모니터링 계획](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[모니터링 배포](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)