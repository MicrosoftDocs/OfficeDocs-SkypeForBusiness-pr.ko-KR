---
title: 백업-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업 하 고 사이트 공유 디렉터리 아래의 CA 폴더에 저장 합니다.
ms.openlocfilehash: 463aab2516deec5b47e549aec67bcba6a0a80bc0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196491"
---
# <a name="backup-cccertificationauthority"></a>백업-CcCertificationAuthority
 
CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업 하 고 사이트 공유 디렉터리 아래의 CA 폴더에 저장 합니다.
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 인증 기관 서비스를 파일에 백업 하 고 사이트 공유 디렉터리 아래의 CA 폴더에 저장 합니다.
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

재해가 발생 했을 때와 동일한 인증서를 사용 하 여 클라우드 커넥터 기기를 다시 배포 하려는 경우 또는 기기를 새 하드웨어로 이동 하려는 경우 인증 기관 백업이 유용할 수 있습니다. 명령이 AD 서버에서 클라우드 커넥터 인증 기관 서비스의 복사본을 "\<SITEROOTDIRECTORY\>\CA\SfB CCE Root. p12"로 저장 합니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. CcCertificationAuthority cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[제거-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

