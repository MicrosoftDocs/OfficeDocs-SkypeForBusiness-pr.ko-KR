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
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리 아래의 CA 폴더에 저장합니다.
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675460"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

Backup-CcCertificationAuthority cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 인증 기관 서비스를 파일에 백업합니다. 또한 cmdlet은 사이트 공유 디렉터리 아래의 CA 폴더에 저장합니다.

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>매개 변수

없음

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예제에서는 인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리 아래의 CA 폴더에 저장합니다.

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

동일한 인증서를 사용하여 클라우드 커넥터 어플라이언스 다시 배포하려는 경우 인증 기관 백업이 유용할 수 있습니다. 예:

- 재해 복구.
- 어플라이언스 새 하드웨어로 이동합니다.

이 명령은 클라우드 커넥터 인증 기관 서비스의 복사본을 AD 서버 `"<SiteRootDirectory>\CA\SfB CCE Root.p12"`에서 .로 저장합니다.

## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 Backup-CcCertificationAuthority cmdlet은 파이프라인된 입력을 허용하지 않습니다.

## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음

## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  