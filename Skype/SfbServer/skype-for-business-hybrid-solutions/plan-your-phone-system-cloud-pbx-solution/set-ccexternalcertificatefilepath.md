---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Set-CcExternalCertificateFilePath cmdlet은 중재 서버 또는 Edge 서버의 인증서가 저장 되는 경로를 지정 합니다.
ms.openlocfilehash: e71a50f09a4ce3d085746c30f7591e8a07eb38de
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003208"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
Set-CcExternalCertificateFilePath cmdlet은 중재 서버 또는 Edge 서버의 인증서가 저장 되는 경로를 지정 합니다.
  
이 인증서는 배포 중에 또는 비즈니스용 Skype 클라우드 커넥터 에디션의 새 기기를 추가할 때 필요 합니다. 이 명령을 사용 하면 배포 후 중재 서버에 대 한 새 인증서를 가져올 수도 있습니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 Edge 서버의 인증서 경로를 설정 합니다.
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>예제 2

다음 예에서는 중재 서버용 인증서 경로를 설정 합니다.
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>예제 3

다음 예제에서는 중재 서버에 대 한 인증서를 업데이트 합니다.
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

배포 중에 또는 토폴로지를 수정 하는 동안에는 Edge 서버 인증서에 대 한 경로를 지정 하 고 필요에 따라 중재 서버 인증서를 선택 해야 합니다. 
  
게이트웨이 및 중재 서버 간에 TLS를 사용 하는 경우 중재 서버용 인증서가 필요 합니다. 클라우드 커넥터 기기를 배포 하 고 TLS를 배포 하려는 경우 중재 서버에 배포 될 인증서의 경로만 지정할 수 있습니다. 그러나 이미 배포 된 기기에서 중재 인증서를 업데이트 하려는 경우 경로와-Import 매개 변수를 지정 해야 합니다. 경로를 보려면 Get-CCExternalCertificateFilePath cmdlet을 사용 합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 대상 <br/> | 필수 <br/> |System.String  <br/> |요청 된 파일 경로 유형입니다. 유형에는 다음이 포함 됩니다.  <br/> EdgeServer (기본값)  <br/> MediationServer  <br/> |
|Import  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |자격 증명을 중재 서버로 가져와야 함을 나타냅니다. 처음으로 기기를 배포 하는 경우이 매개 변수는 필요 하지 않습니다. 이미 배포 된 버전에서 기존 인증서를 변경 하려는 경우에는 매개 변수가 필요 합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

Set-CcExternalCertificateFilePath cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

