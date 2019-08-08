---
title: 비즈니스용 Skype 클라이언트에서 설치 명령줄 옵션 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '요약: Office 설치 프로그램의 setup.exe 명령줄 작업에 대해 알아봅니다.'
ms.openlocfilehash: a84c1f8a69bdff07dfec5e274932a522bf139c9a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234838"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>비즈니스용 Skype 클라이언트에서 설치 명령줄 옵션 사용
 
**요약:** Office 설치 프로그램의 setup.exe 명령줄 작업에 대해 알아봅니다.
  
Setup.exe 명령줄은 Office 설치 프로그램의 매우 적은 작업에 사용 됩니다. 설치 명령줄 옵션을 사용 하는 대신 일반적으로 Office 사용자 지정 도구 및 Config .xml 파일을 사용 하 여 제품 설정 및 기능을 사용자 지정 합니다.
  
Office Setup.exe 명령줄은 다음 표에 설명 된 명령줄 옵션을 인식 합니다.
  
**Office 설치 명령줄 옵션**

|**설치 명령줄 옵션**|**설명**|
|:-----|:-----|
|/admin  <br/> |Office 사용자 지정 도구를 실행 하 여 설치 사용자 지정 파일 (.msp 파일)을 만듭니다.  <br/> |
|/adminfile [path]  <br/> |설치에 지정 된 설치 사용자 지정 파일을 적용 합니다. 특정 사용자 지정 파일 (.msp 파일) 또는 사용자 지정 파일을 저장 하는 폴더에 대 한 경로를 지정할 수 있습니다.  <br/> |
|/config [path]  <br/> |설치 중에 설치 하는 Config.xml 파일을 지정 합니다. /Config 옵션을 사용 하 여 비즈니스용 Skype 설치를 위해 사용자 지정한 Config.xml 파일을 지정 합니다 예:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/Skype 수정  <br/> |수정 된 Config.xml 파일을 사용 하 여 유지 관리 모드에서 설치 프로그램을 실행 하 고 기존 Office 설치를 변경할 수 있습니다. 예를 들어/수정 옵션을 사용 하 여 비즈니스용 Skype 기능을 추가 하거나 제거할 수 있습니다.  <br/> |
|/repair Skype  <br/> |사용자의 컴퓨터에서 설치 프로그램을 실행 하 여 비즈니스용 Skype를 복구 합니다.  <br/> |
|/uninstall Skype  <br/> |설치 프로그램을 실행 하 여 사용자 컴퓨터에서 비즈니스용 Skype를 제거 합니다.  <br/> |
   


