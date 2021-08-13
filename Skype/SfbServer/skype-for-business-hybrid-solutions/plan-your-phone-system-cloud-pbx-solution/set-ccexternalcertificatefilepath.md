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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: 이 Set-CcExternalCertificateFilePath cmdlet은 중재 서버 또는 에지 서버의 인증서가 저장되는 경로를 지정합니다.
ms.openlocfilehash: 7b9b494b27f3ed05dd1ef1cdb91bd583abf2d2b391f1a49c0b2615fd3485187c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344567"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
이 Set-CcExternalCertificateFilePath cmdlet은 중재 서버 또는 에지 서버의 인증서가 저장되는 경로를 지정합니다.
  
이 인증서는 배포 중에 또는 새 어플라이언스를 추가할 때 비즈니스용 Skype 클라우드 커넥터 버전. 또한 이 명령은 배포 후에 중재 서버에 대한 새 인증서를 가져올 수 있습니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 에지 서버의 인증서 경로를 설정합니다.
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>예 2

다음 예에서는 중재 서버의 인증서 경로를 설정합니다.
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>예 3

다음 예제에서는 중재 서버의 인증서를 업데이트합니다.
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

배포 중이나 토폴로지 수정 중에 에지 서버 인증서의 경로와 중재 서버 인증서에 대한 경로를 선택적으로 지정해야 합니다. 
  
게이트웨이와 중재 서버 간에 TLS를 사용하려면 중재 서버에 대한 인증서가 필요합니다. 클라우드 커넥터 어플라이언스를 배포하고 TLS를 배포하려는 경우 중재 서버에 배포할 인증서의 경로만 지정할 수 있습니다. 그러나 이미 배포된 어플라이언스에서 중재 인증서를 업데이트하려면 경로 및 -Import 매개 변수를 지정해야 합니다. 경로를 표시하기 위해 Get-CCExternalCertificateFilePath cmdlet을 사용 합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 대상 <br/> | 필수 <br/> |System.String  <br/> |요청된 파일 경로의 유형입니다. 형식은 다음과 같습니다.  <br/> EdgeServer(기본값)  <br/> MediationServer  <br/> |
|가져오기  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |인증서를 중재 서버로 가져와야 를 나타냅니다. 어플라이언스를 처음 배포하는 경우 이 매개 변수는 필요하지 않습니다. 이미 배포된 버전에서 기존 인증서를 변경하려면 매개 변수가 필요합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

이 Set-CcExternalCertificateFilePath cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

