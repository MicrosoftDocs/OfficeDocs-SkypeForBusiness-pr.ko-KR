---
title: Backup-CcCertificationAuthority
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
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: 이 Backup-CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리의 CA 폴더에 저장합니다.
ms.openlocfilehash: abf94977abe2a0c3548b549ae0101ae399e124769eaaa9f05aabf203c69656a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282960"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
이 Backup-CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리의 CA 폴더에 저장합니다.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리의 CA 폴더에 저장합니다.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

인증 기관 백업은 재해 발생 시 동일한 인증서를 사용하여 Cloud Connector 어플라이언스를 다시 설치하려는 경우 또는 어플라이언스를 새 하드웨어로 이동하려는 경우에 유용할 수 있습니다. 이 명령은 클라우드 커넥터 인증 기관 서비스의 복사본을 AD Server의 " \<SiteRootDirectory\> \CA\SfB CCE Root.p12"로 저장합니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Backup-CcCertificationAuthority cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

