---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Cloud Connector 어플라이언스 버전을 반환합니다. Get-CCVersion 커넥터의 호스트 머신에서만 사용할 수 있습니다.
ms.openlocfilehash: d3da9813fd67228f8e198cd21edce3cc187ac9359617eb660a352b38c51a95ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349510"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Cloud Connector 어플라이언스 버전을 반환합니다. Get-CCVersion 커넥터의 호스트 머신에서만 사용할 수 있습니다.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>자세한 정보

설치된 PowerShell 스크립트, Appliance 디렉터리의 파일 및 호스트 서버에 배포된 가상 컴퓨터를 기반으로 하는 Cloud Connector 어플라이언스 버전을 반환합니다.
  
## <a name="parameters"></a>매개 변수

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |옵션  <br/> |System.String  <br/> |버전 유형입니다. 매개 변수 값은 RunningScripts, RunningBits, BackupBits 또는 All일 수 있습니다. 기본값은 RunningScripts입니다.  <br/> |
   
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예제에서는 열려 있는 PowerShell 콘솔에서 현재 실행 중인 스크립트의 클라우드 커넥터 버전을 보여줍니다.
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>예 2

다음 예에서는 가상 머신에 배포된 현재 실행 중인 이진의 클라우드 커넥터 버전을 보여 주며, Hyper-v 관리자에서 실행 중인 가상 컴퓨터 이름에서 버전을 볼 수 있습니다.
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>입력 형식
<a name="Examples"> </a>

없음 이 Get-CcVersion cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="Examples"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="Examples"> </a>

없음
  

