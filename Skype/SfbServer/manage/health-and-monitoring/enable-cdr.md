---
title: 비즈니스용 Skype 서버에서 통화 정보 기록 사용
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
description: '요약: 비즈니스용 Skype 서버에서 CDR(통화 정보 기록) 레코드를 사용하도록 설정하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816888"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 통화 정보 기록 사용

**요약:** 비즈니스용 Skype 서버에서 CDR(통화 정보 기록) 레코드를 사용하도록 설정하는 방법을 자세히 알아보습니다.

CDR(통화 정보 기록)은 인스턴트 메시징, VoIP(Voice over Internet Protocol) 통화, 응용 프로그램 공유, 파일 전송, 모임 등의 피어 투 피어 활동에 대한 사용 및 진단 정보를 기록합니다. 이러한 사용 데이터는 ROI(투자 수익률)를 계산하는 데 사용하고, 진단 데이터는 피어-투-피어 활동 및 모임 관련 문제를 해결하는 데 사용할 수 있습니다.

다음 절차에 따라 조직의 각 사이트 또는 조직 전체에 대해 CDR을 사용하도록 설정합니다.

> [!NOTE]
> CDR을 사용하도록 설정하려면 먼저 모니터링 및 모니터링 데이터베이스를 구성해야 합니다. 자세한 내용은 [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)를 참조하십시오.

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판에서 CDR을 사용하도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **통화 정보 기록** 을 클릭합니다.

4. **통화 정보 기록** 페이지의 표에서 적절한 사이트를 클릭하고 **동작** 을 클릭한 후에 **CDR 사용** 을 클릭합니다.

    > [!NOTE]
    > CDR은 기본적으로 사용하도록 설정됩니다.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 CDR Windows PowerShell 사용

**SET-CsCdrConfiguration** cmdlet과 Windows PowerShell CDR을 사용하도록 설정할 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 이 cmdlet을 실행할 수 Windows PowerShell. 원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.

### <a name="to-enable-cdr-for-a-single-location"></a>단일 위치에 대해 CDR을 사용하도록 설정하려면

 CDR을 사용하도록 설정하려면 EnableCDR 매개 변수를 True($True)로 설정합니다.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>단일 위치에 대해 CDR을 사용하지 않도록 설정하려면

 CDR을 사용하지 않도록 설정하려면 EnableCDR 매개 변수를 False($False)로 설정합니다. CDR을 설정하지 않는 경우 모니터링이 제거되지 않습니다. CDR 데이터의 수집 및 저장을 일시 중지합니다.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>단일 명령을 사용하여 여러 위치에서 CDR을 사용하도록 설정하려면

 다음 명령은 조직에서 현재 사용 중인 모든 CDR 구성 설정에 대해 CDR을 사용하도록 설정합니다.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

자세한 내용은 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="see-also"></a>참고 항목

[모니터링 계획](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[모니터링 배포](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
