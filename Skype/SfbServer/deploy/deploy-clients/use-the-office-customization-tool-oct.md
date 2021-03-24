---
title: 비즈니스용 Skype 서버에서 OCT(Office 사용자 지정 도구) 사용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '요약: 비즈니스용 Skype 클라이언트에서 Office 사용자 지정 도구를 사용하는 방법'
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100454"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 OCT(Office 사용자 지정 도구) 사용
 
**요약:** 비즈니스용 Skype 클라이언트에서 Office 사용자 지정 도구를 사용하는 방법
  
OCT(Office 사용자 지정 도구)는 설치 프로그램의 일부로, 많은 사용자 지정에 권장되는 도구입니다. OCT를 사용하여 Office를 사용자 지정하고 설치 사용자 지정 .msp 파일에 사용자 지정을 저장합니다. 이 파일은 네트워크 설치 지점의 Updates 폴더에 저장합니다. Office를 설치하면 설치 프로그램이 Updates 폴더에서 설치 사용자 지정 파일을 검색하고 사용자 지정을 적용합니다. Updates 폴더는 Office 초기 설치 중에 소프트웨어 업데이트를 배포하는 데만 사용할 수 있습니다.
  
OCT는 설치의 일부로, 제품의 볼륨 라이선스 버전에만 사용됩니다. Office 원본 파일이 포함된 네트워크 설치 지점의 루트에서 명령줄에 입력하여  `setup.exe /admin` OCT를 실행합니다. 예를 들어 다음을 사용 합니다.
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
관리자는 OCT를 사용하여 설치 사용자 지정 .msp 파일을 만들고 다음 영역을 사용자 지정할 수 있습니다.
  
- **설치** 클라이언트 및 기본 조직 이름, 추가 네트워크 설치 원본, 제품 키, 최종 사용자 사용권 계약, 표시 수준, 제거할 이전 버전의 Office, 설치 중에 실행할 사용자 지정 프로그램, 보안 설정 및 설치 속성을 지정하는 데 사용됩니다.
    
- **기능** 사용자 설정을 구성하고 Office 기능이 설치되는 방법을 사용자 지정하는 데 사용됩니다. 관리자는 OCT를 사용하여 사용자에 대한 Office 응용 프로그램 설정의 초기 기본값을 지정할 수 있습니다. 사용자는 설치 후 대부분의 설정을 수정할 수 있습니다.
    
- **추가 콘텐츠** 파일을 추가 또는 제거하고, 레지스트리 항목을 추가 또는 제거하고, 바로 가기를 구성하는 데 사용됩니다.
    
- **Outlook** 사용자의 기본 Outlook 프로필을 사용자 지정하고, Exchange 설정을 지정하고, 계정을 추가하고, 계정을 제거하고, 설정을 내보내고, 보내기/받기 그룹을 지정하는 데 사용됩니다.
    
OCT에 대한 자세한 내용은 [Use the OCT to customize Office 2013을 참조하십시오.](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) 이 정보는 이후 버전의 Office에도 적용됩니다.
