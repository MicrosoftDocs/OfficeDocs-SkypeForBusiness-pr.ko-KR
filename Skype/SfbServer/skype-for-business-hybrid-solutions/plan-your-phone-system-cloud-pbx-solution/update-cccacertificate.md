---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: 이 Update-CcCACertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신합니다.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824122"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
이 Update-CcCACertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전 루트 CA 인증서를 갱신합니다. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 루트 CA 인증서를 갱신합니다. 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

클라우드 커넥터 루트 CA 인증서는 인증 기관 서비스가 설치된 날짜로부터 5년 동안 유효합니다.
  
루트 인증서가 만료에 가까운 경우 또는 이미 만료된 경우 Update-CcCACertificate cmdlet을 실행하여 인증서를 갱신합니다. 루트 인증서가 갱신된 후 AD Server, 중앙 관리 저장소 및 에지 서버는 자동으로 새 인증서를 발급합니다.
  
동일한 PSTN 사이트에 여러 어플라이언스가 있는 경우 동일한 PSTN 사이트의 모든 어플라이언스에서 Update-CcCACertificate cmdlet을 실행합니다.
  
마지막 Export-CcRootCertificate 실행하여 루트 인증서를 첫 번째 어플라이언스의 로컬 파일로 내보냈다가 내보냈던 인증서를 PSTN 게이트웨이에 복사하여 설치합니다.
  
이 명령은 Cloud Connector 2.0 Renew-CcCACertificate 릴리스의 cmdlet을 대체합니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Update-CcCACertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음 
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

