---
title: Config.xml을 사용 하 여 비즈니스용 Skype 클라이언트에서 설치 작업 수행
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: '요약: Config.xml 파일을 사용 하 여 추가 설치 지침을 지정 하는 방법입니다.'
ms.openlocfilehash: a935e3623e99324eb24caef4e7e232d2311c5cfb
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768651"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Config.xml을 사용 하 여 비즈니스용 Skype 클라이언트에서 설치 작업 수행

**요약:** Config.xml 파일을 사용 하 여 추가 설치 지침을 지정 하는 방법을 설명 합니다.

OCT (Office 사용자 지정 도구)는 사용자 지정 설치에 대 한 기본 도구 이지만 관리자는 Config.xml 파일을 사용 하 여 OCT에서 사용할 수 없는 추가 설치 지침을 지정할 수 있습니다. 다음 사용자 지정은 Config.xml 파일만을 사용 하 여 만들 수 있습니다.

- 네트워크 설치 지점의 경로를 지정 합니다.

- 설치할 제품을 선택 합니다.

- 로깅 및 설치 사용자 지정 파일 및 소프트웨어 업데이트의 위치를 구성 합니다.

- 사용자 이름 등의 설치 옵션을 지정 합니다.

- Office를 설치 하지 않고 사용자의 컴퓨터에 LIS (로컬 설치 원본)를 복사 합니다.

- 설치에서 언어를 추가 하거나 제거 합니다.

Config.xml 파일을 사용 하 여 비즈니스용 Skype 자동 설치를 구성 하는 것이 좋습니다. 

기본적으로 core product 폴더에 저장 된 Config.xml 파일입니다 (예: \ _product_. WW) 설치 프로그램이 해당 제품을 설치 하도록 지시 합니다. 예를 들어 다음 폴더의 Config.xml 파일은 비즈니스용 Skype를 설치 합니다.

- \\server\share\Skype15\Skype.WW \Configxml

비즈니스용 Skype 설치에 가장 일반적으로 사용 되는 Config.xml 요소는 다음 표에 나열 되어 있습니다.

**Config.xml 요소**


| **요소**              | **설명**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 구성  <br/>     | 최상위 수준 요소 (필수). Product = Lync (비즈니스용 Skype 클라이언트용으로 작동 하는 제품) 특성을 포함 합니다.  <br/>                                                                                                                                                          |
| 없음 상태  <br/>       | 설치 중에 특정 제품 기능을 처리 하는 방법을 지정 합니다. 다음 특성을 사용 하 여 Outlook에 방해가 되는 공유 구성 요소를 포함 하는 Business Connectivity Services의 설치를 방지 합니다. <br/>  Id = "주 Imain" <br/>  State = "없음" <br/>  Children = "Force" <br/> |
| 표시  <br/>           | 설치 프로그램이 사용자에 게 표시 하는 UI 수준입니다. 일반적인 특성에는 다음이 포함 됩니다. <br/>  고 지 사항 = "예"                                                                                                                                                                                |
| 로깅하  <br/>           | 설정이 수행 하는 로깅 종류에 대 한 옵션입니다. 일반적인 특성에는 다음이 포함 됩니다. <br/>  Type = "Off"                                                                                                                                                                                       |
| 설정  <br/>           | Windows Installer 속성에 대 한 값을 지정 합니다. 일반적인 특성에는 다음이 포함 됩니다. <br/>  설정 Id = " *name*" (Windows Installer 속성의 이름)  <br/>  값 = " *값*" (속성에 할당할 값)  <br/>                                                             |
| DistributionPoint  <br/> | 설치를 실행할 네트워크 설치 지점의 정규화 된 경로입니다. Location 특성을 포함 합니다. <br/>  위치 = " *path*"  <br/>                                                                                                                                     |

다음 예제에서는 비즈니스용 Skype 클라이언트의 일반적인 자동 설치에 대 한 Config.xml 파일을 보여 줍니다. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Config.xml 파일을 사용 하 여 Office 설치 및 유지 관리 작업을 수행 하는 방법에 대 [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)한 자세한 내용은에서 확인할 수 있습니다.

## <a name="to-customize-the-configxml-file"></a>Config.xml 파일을 사용자 지정 하려면

1. 메모장과 같은 텍스트 편집기 도구를 사용 하 여 Config.xml 파일을 엽니다.

2. 변경 하려는 요소가 포함 된 선을 찾습니다.

3. 사용할 자동 옵션으로 요소 항목을 수정 합니다. 주석 구분 기호 "\<!--" 및 "--\>"을 제거 해야 합니다. 예를 들어 다음 구문을 사용 합니다.

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Config.xml 파일을 저장 합니다.


