---
title: 클라이언트 Config.xml 사용하여 클라이언트에서 설치 비즈니스용 Skype 수행
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: '요약: Config.xml 파일을 사용하여 추가 설치 지침을 지정하는 방법'
ms.openlocfilehash: e0dcc16a09540965346ea014a8c39be0470e4f09
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858675"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>클라이언트 Config.xml 사용하여 클라이언트에서 설치 비즈니스용 Skype 수행

**요약:** 추가 설치 Config.xml 지정하는 방법

사용자 지정 설치에는 기본적으로 OCT(Office 사용자 지정 도구)가 사용되기는 하지만, 관리자는 Config.xml 파일을 사용하여 OCT에서 사용할 수 없는 추가 설치 지침을 지정할 수 있습니다. Config.xml 파일을 통해서만 수행할 수 있는 사용자 지정 작업은 다음과 같습니다.

- 네트워크 설치 지점 경로 지정

- 설치할 제품 선택

- 설치 사용자 지정 파일 및 소프트웨어 업데이트의 위치와 로깅 구성

- 사용자 이름 등의 설치 옵션 지정

- Office를 설치하지 않고 사용자 컴퓨터에 LIS(로컬 설치 원본) 복사

- 설치에서 언어 추가 또는 제거

자동 설치를 구성하기 위해 Config.xml 파일을 비즈니스용 Skype 것이 좋습니다. 

기본적으로 핵심 Config.xml 폴더(예: \ 제품)에 저장된 기본 _파일입니다._ WW) 설치 프로그램이 이 제품을 설치하도록 지시합니다. 예를 들어 다음 폴더의 Config.xml 파일을 설치하면 다음 비즈니스용 Skype.

- \\server\share\Skype15\Skype. WW \Config.xml

Config.xml 설치에 가장 일반적으로 사용되는 비즈니스용 Skype 요소는 다음 표에 나와 있습니다.

**Config.xml 요소**


| **요소**              | **설명**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 구성  <br/>     | 최상위 요소(필수)입니다. Product 특성(예: Product=Lync)을 포함(비즈니스용 Skype 클라이언트에 대해 작동)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | 특정 제품 기능이 설치 중에 처리되는 방법을 지정합니다. 다음 특성을 사용하여 Business Connectivity 방해하는 공유 구성 요소를 포함하는 Outlook. <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| 표시  <br/>           | 설치 프로그램에서 사용자에게 표시하는 UI의 수준입니다. 일반적인 특성은 다음과 같습니다. <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| 로깅  <br/>           | 설치 프로그램이 수행하는 로깅 종류에 대한 옵션입니다. 일반적인 특성은 다음과 같습니다. <br/>  Type ="Off"                                                                                                                                                                                       |
| 설정  <br/>           | Windows Installer 속성의 값을 지정합니다. 일반적인 특성은 다음과 같습니다.<br/>  Setting Id=" *name*" (the name of the Windows Installer property)  <br/>  Value=" *값*" (속성에 할당할 값)  <br/>                                                             |
| DistributionPoint  <br/> | 설치를 실행할 네트워크 설치 지점의 정규화된 경로입니다. Location 특성을 포함합니다.<br/>  Location=" *path*"  <br/>                                                                                                                                     |

다음 예제에서는 Config.xml 클라이언트의 일반적인 자동 설치에 대한 비즈니스용 Skype 보여줍니다. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Config.xml 파일을 사용하여 설치 및 유지 관리 Office 수행하는 자세한 정보는 에서 사용할 수 [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) 있습니다.

## <a name="to-customize-the-configxml-file"></a>Config.xml 파일을 사용자 지정하려면

1. 메모장과 같은 텍스트 편집기 도구를 사용하여 Config.xml 파일을 엽니다.

2. 변경할 요소가 포함된 줄을 찾습니다.

3. 요소 항목을 사용하려는 자동 옵션으로 수정합니다. 주석 분리기 " "를 제거해야 \<!--" and "--\> 합니다. 예를 들어 다음과 같은 구문을 사용할 수 있습니다.

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Config.xml 파일을 저장합니다.