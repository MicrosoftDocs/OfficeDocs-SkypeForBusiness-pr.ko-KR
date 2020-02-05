---
title: 비즈니스용 Skype 서버에서 OCT (Office 사용자 지정 도구) 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '요약: 비즈니스용 Skype 클라이언트에서 Office 사용자 지정 도구를 사용 하는 방법을 설명 합니다.'
ms.openlocfilehash: d5b9e5363f56842675831c4b3c0fe3582fb6d02a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768451"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 OCT (Office 사용자 지정 도구) 사용
 
**요약:** 비즈니스용 Skype 클라이언트에서 Office 사용자 지정 도구를 사용 하는 방법을 설명 합니다.
  
OCT (Office 사용자 지정 도구)는 설치 프로그램의 일부 이며 많은 사용자 지정에 권장 되는 도구입니다. OCT를 사용 하 여 Office를 사용자 지정 하 고 설치 사용자 지정 .msp 파일에 사용자 지정을 저장 합니다. 네트워크 설치 지점의 Updates 폴더에 파일을 배치 합니다. Office를 설치 하면 설치 프로그램이 Updates 폴더에서 설치 사용자 지정 파일을 찾고 사용자 지정을 적용 합니다. 업데이트 폴더는 Office 최초 설치 중에 소프트웨어 업데이트를 배포 하는 데에만 사용할 수 있습니다.
  
OCT는 설치 프로그램의 일부 이며 볼륨 라이선스 버전의 제품에만 사용 됩니다. Office 원본 파일을 포함 하 `setup.exe /admin` 는 네트워크 설치 지점의 루트에 있는 명령줄을 입력 하 여 OCT를 실행 합니다. 예를 들어 다음을 사용 합니다.
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
관리자는 OCT를 사용 하 여 설치 사용자 지정 .msp 파일을 만들고 다음 영역을 사용자 지정할 수 있습니다.
  
- **설정** 클라이언트 및 기본 조직 이름, 추가 네트워크 설치 원본, 제품 키, 최종 사용자 사용권 계약, 표시 수준, 제거 하려는 Office 버전, 설치 중에 실행 되는 사용자 지정 프로그램, 보안 설정, 설치 속성에 대 한 기본 설치 위치를 지정 하는 데 사용 됩니다.
    
- **기능** 사용자 설정을 구성 하 고 Office 기능을 설치 하는 방법을 사용자 지정 하는 데 사용 됩니다. 관리자는 OCT를 사용 하 여 사용자에 대 한 Office 응용 프로그램 설정의 초기 기본 값을 지정할 수 있습니다. 설치 후 사용자가 대부분의 설정을 수정할 수 있습니다.
    
- **추가 콘텐츠** 파일을 추가 또는 제거 하 고, 레지스트리 항목을 추가 또는 제거 하 고, 바로 가기를 구성 하는 데 사용 됩니다.
    
- **Outlook** 사용자의 기본 Outlook 프로필을 사용자 지정 하 고, Exchange 설정을 지정 하 고, 계정 추가, 계정 제거 및 설정 내보내기를 하 고, Send\Receive 그룹을 지정 하는 데 사용 됩니다.
    
OCT에 대 한 자세한 내용은 [oct를 사용 하 여 Office 2013 사용자 지정](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))을 참조 하세요. 이 정보는 최신 버전의 Office에도 적용 됩니다.
  

