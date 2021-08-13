---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: 이 Get-CcExternalCertificateFilePath cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 배포에 대한 외부 인증서 파일 경로를 반환합니다. 사용자가 이 인증서를 준비합니다.
ms.openlocfilehash: 3f0a3bc761beb1a2aa1c88bfabf509e4aef17b012f52e04be1ec5944df73ba9c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315384"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
이 Get-CcExternalCertificateFilePath cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 배포에 대한 외부 인증서 파일 경로를 반환합니다. 사용자가 이 인증서를 준비합니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 에지 서버의 인증서 경로를 보여 주며,
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>예 2

다음 예에서는 중재 서버에 대한 인증서 집합을 보여 제공합니다.
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

배포 중이나 토폴로지 수정 중에는 에지 서버 인증서의 경로와 중재 서버의 경로를 선택적으로 지정해야 합니다. 게이트웨이와 중재 서버 간에 TLS를 사용하려면 중재 서버에 대한 인증서가 필요합니다. 경로를 변경하기 위해 Set-CcExternalCertificateFilePath cmdlet을 사용 합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|대상  <br/> |선택  <br/> | System.Management.Automation.SwitchParameter <br/> |요청된 파일 경로의 유형입니다. 형식은 다음과 같습니다.  <br/> EdgeServer(기본값)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

이 Get-CcExternalCertificateFilePath cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

명령은 파일 경로를 반환합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

