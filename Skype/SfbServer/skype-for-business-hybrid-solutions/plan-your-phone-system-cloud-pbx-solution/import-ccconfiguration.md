---
title: 가져오기-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 로컬 파일에서 클라우드 커넥터 호스트 서버로의 비즈니스용 Skype 클라우드 커넥터 에디션 구성을 가져옵니다.
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190743"
---
# <a name="import-ccconfiguration"></a>가져오기-CcConfiguration
 
로컬 파일에서 클라우드 커넥터 호스트 서버로의 비즈니스용 Skype 클라우드 커넥터 에디션 구성을 가져옵니다.
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 클라우드 커넥터 인스턴스의 기기 디렉터리에서%SystemDrive%\ProgramData\CloudConnector 디렉터리로 CloudConnector .ini를 복사 합니다.
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>자세한 정보
<a name="Examples"> </a>

이 cmdlet은 클라우드 커넥터 기기의 기기 디렉터리에서%SystemDrive%\ProgramData\CloudConnector 디렉터리로 CloudConnector .ini을 복사 합니다. CcApplianceDirectory cmdlet을 사용 하 여 기기 디렉터리를 지정 합니다. Cmdlet이%SystemDrive%\ProgramData\CloudConnector.의 모든 기존 파일을 덮어씁니다. 이 명령은 Cloud Connector Edition 버전 2.0.1 이상에 적용 됩니다.
  
## <a name="parameters"></a>매개 변수
<a name="Examples"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |통지 없이%SystemDrive%\ProgramData\CloudConnector의 기존 파일을 덮어씁니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="Examples"> </a>

없음. 가져오기-CcConfiguration cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="Examples"> </a>

없음.
  
## <a name="see-also"></a>참고 항목
<a name="Examples"> </a>

수출-CcConfiguration
  

