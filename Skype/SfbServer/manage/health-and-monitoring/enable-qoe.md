---
title: 비즈니스용 Skype 서버에서 환경 품질 사용
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
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '요약: 비즈니스용 Skype 서버에서 QoE(QoE)를 사용하도록 설정하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 67b752df3791d3ba0493a7e3575f25c58231ad26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816858"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 환경 품질 사용

**요약:** 비즈니스용 Skype 서버에서 QoE(QoE)를 사용하도록 설정하는 방법을 설명하는 정보를 제공합니다.

QoE(체감 품질)는 통화 및 세션에 포함된 참가자, 장치 이름, 드라이버, IP 주소, 끝점 유형에 대한 정보 및 미디어의 품질을 나타내는 숫자 데이터를 기록합니다. 자세한 내용은 계획 설명서에서 [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)을 참조하십시오.

다음 절차를 사용하여 전체 조직이나 조직의 각 사이트에 대해 QoE를 사용하도록 설정할 수 있습니다.

> [!NOTE]
> QoE를 사용하도록 설정하려면 먼저 모니터링 및 모니터링 백 엔드 데이터베이스를 구성해야 합니다. 자세한 내용은 [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)를 참조하십시오.

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 QoE를 사용하도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **체감 품질 데이터** 를 클릭합니다.

4. **체감 품질 데이터** 페이지의 테이블에서 적합한 컬렉션을 클릭하고 **동작**, **QoE 사용** 을 차례로 클릭합니다.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Cmdlet을 사용하여 QoE Windows PowerShell 사용

**Set-CsQoEConfiguration cmdlet과 set-CsQoEConfiguration** cmdlet을 Windows PowerShell QoE를 사용하도록 설정할 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 이 cmdlet을 실행할 수 Windows PowerShell. 원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.

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

자세한 내용은 [Set-CsQoEConfiguration을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>참고 항목

[모니터링 계획](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[모니터링 배포](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

