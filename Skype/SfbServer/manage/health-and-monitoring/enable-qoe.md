---
title: 비즈니스용 Skype 서버에서 환경 품질 사용
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
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '요약: 비즈니스용 Skype 서버에서 환경 품질 (체감 품질)을 사용 하도록 설정 하는 방법을 알아봅니다.'
ms.openlocfilehash: bc757748e9d95c92405a7dc9a72f87b869165825
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817968"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 환경 품질 사용

**요약:** 비즈니스용 Skype 서버에서 환경 품질 (체감 품질)을 사용 하도록 설정 하는 방법을 알아봅니다.

환경 품질 (체감 품질)은 통화 및 세션과 관련 된 참가자, 장치 이름, 드라이버, IP 주소, 끝점 형식에 대 한 미디어 품질과 정보를 표시 하는 숫자 데이터를 기록 합니다. 자세한 내용은 계획 설명서의 [모니터링 계획](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 을 참조 하세요.

조직의 전체 조직 또는 각 사이트에 대해 체감 품질을 사용 하도록 설정 하려면 다음 절차를 사용 합니다.

> [!NOTE]
> 체감 품질을 사용 하도록 설정 하려면 먼저 모니터링과 모니터링 백 엔드 데이터베이스를 구성 해야 합니다. 자세한 내용은 [모니터링 배포](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)를 참조 하세요.

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 체감 품질을 사용 하도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .

2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.

4. **경력 데이터** 페이지에서 테이블의 적절 한 컬렉션을 클릭 하 고 **작업**을 클릭 한 다음 **체감 품질 사용**을 클릭 합니다.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 체감 품질 사용

Windows PowerShell 및 **Set-CsQoEConfiguration** cmdlet을 사용 하 여 체감 품질를 사용 하도록 설정할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.

### <a name="to-enable-qoe-for-a-single-location"></a>단일 위치에 대해 체감 품질을 사용 하도록 설정 하려면

 체감 품질을 사용 하도록 설정 하려면 EnableQoE 매개 변수를 True ($True)로 설정 합니다.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>단일 위치에 대해 체감 품질를 사용 하지 않도록 설정 하려면

 체감 품질를 사용 하지 않으려면 EnableQoE 매개 변수를 False ($False)로 설정 합니다. 이는 모니터링을 제거 하지 않습니다. 체감 품질 데이터의 컬렉션 및 저장소를 일시 중지 합니다.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>단일 명령을 사용 하 여 여러 위치에서 체감 품질을 사용 하도록 설정 하려면

 이 명령은 현재 조직에서 사용 중인 모든 체감 품질 구성 설정에 대해 체감 품질을 사용 하도록 설정 합니다.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

자세한 내용은 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[모니터링 계획](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[모니터링 배포](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

