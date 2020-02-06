---
title: Remove-CcCertificationAuthorityFile
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
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 공유 디렉터리 아래에 있는 CA 폴더의 인증 기관 서비스 백업 파일을 제거 합니다.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824294"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
CcCertificationAuthorityFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 사이트 공유 디렉터리&lt;아래의&gt;CA 폴더에서 "SiteRootDirectory \CA\SfB CCE Root. p12" 인증 기관 서비스 백업 파일을 제거 합니다. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 사이트 공유 디렉터리 아래의 CA 폴더에서 인증&lt;기관&gt;서비스 백업 파일 "SiteRootDirectory \CA\SfB CCE Root: p12"를 제거 합니다.
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. CcCertificationAuthorityFile cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

