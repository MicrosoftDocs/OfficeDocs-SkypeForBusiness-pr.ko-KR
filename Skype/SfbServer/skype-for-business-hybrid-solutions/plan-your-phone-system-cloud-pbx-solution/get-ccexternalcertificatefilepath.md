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
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Get-CcExternalCertificateFilePath cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 배포에 대 한 외부 인증서 파일 경로를 반환 합니다. 사용자가이 인증서를 준비 합니다.
ms.openlocfilehash: 7a471b0e4258728bfaa50558aab54955346b457c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003378"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Get-CcExternalCertificateFilePath cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 배포에 대 한 외부 인증서 파일 경로를 반환 합니다. 사용자가이 인증서를 준비 합니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 Edge 서버용 인증서의 경로를 보여 줍니다.
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>예제 2

다음 예에서는 중재 서버에 대 한 인증서 집합을 보여 줍니다.
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

배포 중 또는 토폴로지를 수정할 때 Edge 서버 인증서의 경로를 지정 하 고 필요에 따라 중재 서버에 대 한 경로를 지정 해야 합니다. 게이트웨이 및 중재 서버 간에 TLS를 사용 하는 경우 중재 서버용 인증서가 필요 합니다. 경로를 변경 하려면 Set-CcExternalCertificateFilePath cmdlet을 사용 합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|대상  <br/> |선택  <br/> | System.Management.Automation.SwitchParameter <br/> |요청 된 파일 경로 유형입니다. 유형에는 다음이 포함 됩니다.  <br/> EdgeServer (기본값)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

Get-CcExternalCertificateFilePath cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

이 명령은 파일 경로를 반환 합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

