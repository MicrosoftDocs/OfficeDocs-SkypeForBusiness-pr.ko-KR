---
title: 다운로드-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 클라우드 커넥터 기기의 버전을 반환 합니다. Get-CCVersion은 클라우드 커넥터의 호스트 컴퓨터 에서만 사용할 수 있습니다.
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190749"
---
# <a name="get-ccversion"></a>다운로드-CcVersion
 
클라우드 커넥터 기기의 버전을 반환 합니다. Get-CCVersion은 클라우드 커넥터의 호스트 컴퓨터 에서만 사용할 수 있습니다.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>자세한 정보

설치 된 PowerShell 스크립트, 기기 디렉터리의 파일, 호스트 서버에 배포 된 가상 컴퓨터에 따라 클라우드 커넥터 기기의 버전을 반환 합니다.
  
## <a name="parameters"></a>매개 변수

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |선택  <br/> |System.String  <br/> |버전 유형입니다. 매개 변수 값은 RunningScripts, RunningBits, BackupBits 또는 All 일 수 있습니다. 기본값은 RunningScripts입니다.  <br/> |
   
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 열려 있는 PowerShell 콘솔에서 현재 실행 중인 스크립트의 클라우드 커넥터 버전을 보여 줍니다.
  
```
Get-CcVersion
```

### <a name="example-2"></a>예제 2

다음 예제에서는 가상 컴퓨터에 배포 된 현재 실행 중인 이진 파일의 클라우드 커넥터 버전을 보여 줍니다. Hyper-v 관리자의 실행 중인 가상 컴퓨터 이름에서 버전을 확인할 수 있습니다.
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>입력 형식
<a name="Examples"> </a>

없음. Get-CcVersion cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="Examples"> </a>

없음.
  
## <a name="see-also"></a>참고 항목
<a name="Examples"> </a>

없음.
  

