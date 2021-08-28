---
title: OCT(Office 사용자 지정 도구)를 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '요약: 사용자 지정 Office 도구와 함께 비즈니스용 Skype 방법을 설명하는 방법을 설명하는 비즈니스용 Skype 있습니다.'
ms.openlocfilehash: d1fa867326ec1c613793831253dc693783132b57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587840"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>OCT(Office 사용자 지정 도구)를 비즈니스용 Skype 서버
 
**요약:** 사용자 지정 도구를 Office 사용자 지정 도구를 비즈니스용 Skype.
  
OCT(Office 사용자 지정 도구)는 설치 프로그램의 일부로, 많은 사용자 지정에 권장되는 도구입니다. OCT를 사용하면 사용자 지정 Office .msp 파일에 사용자 지정을 저장합니다. 이 파일은 네트워크 설치 지점의 Updates 폴더에 저장합니다. 설치 Office 설치 프로그램이 Updates 폴더에서 설치 사용자 지정 파일을 검색하고 사용자 지정을 적용합니다. Updates 폴더는 초기 설치 중에 소프트웨어 업데이트를 배포하는 데만 사용할 수 Office.
  
OCT는 설치의 일부로, 제품의 볼륨 라이선스 버전에만 사용됩니다. OCT를 실행하려면 원본 파일이 포함된 네트워크 설치 지점의 루트에서 `setup.exe /admin` 명령줄에 Office 실행합니다. 예를 들어 다음을 사용 합니다.
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
관리자는 OCT를 사용하여 설치 사용자 지정 .msp 파일을 만들고 다음 영역을 사용자 지정할 수 있습니다.
  
- **설치** 클라이언트 및 기본 조직 이름에 기본 설치 위치, 추가 네트워크 설치 원본, 제품 키, 최종 사용자 사용권 계약, 표시 수준, 제거할 이전 버전의 Office, 설치 중에 실행할 사용자 지정 프로그램, 보안 설정 및 설치 속성을 지정하는 데 사용됩니다.
    
- **기능** 사용자 설정을 구성하고 사용자 Office 사용자 지정하는 데 사용됩니다. 관리자는 OCT를 사용하여 사용자에 대한 응용 프로그램 설정의 Office 지정할 수 있습니다. 사용자는 설치 후 대부분의 설정을 수정할 수 있습니다.
    
- **추가 콘텐츠** 파일을 추가 또는 제거하고, 레지스트리 항목을 추가 또는 제거하고, 바로 가기를 구성하는 데 사용됩니다.
    
- **Outlook** 사용자의 기본 Outlook 사용자 지정하고, Exchange 설정을 지정하고, 계정을 추가하고, 계정을 제거하고, 설정을 내보내고, 보내기/받기 그룹을 지정하는 데 사용됩니다.
    
OCT에 대한 자세한 내용은 [Use the OCT to customize Office 2013을 참조하십시오.](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) 이 정보는 이후 버전의 서비스에서도 Office.
