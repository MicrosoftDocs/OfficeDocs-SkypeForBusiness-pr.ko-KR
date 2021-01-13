---
title: 비즈니스용 Skype 클라이언트에서 설치 명령줄 옵션 사용
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '요약: Office 설치 Setup.exe 명령줄 작업을 설명하는 방법을 제공합니다.'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837208"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>비즈니스용 Skype 클라이언트에서 설치 명령줄 옵션 사용
 
**요약:** Office 설치 Setup.exe 명령줄 작업에 대해 자세히 알아보습니다.
  
Setup.exe 명령줄이 사용되는 Office 설치 작업은 매우 한정적입니다. 설치 명령줄 옵션을 사용하는 대신 일반적으로 제품 설정 및 기능 사용자 지정에 Office 사용자 지정 도구와 Config.xml 파일을 사용합니다.
  
다음 표에는 Office Setup.exe 명령줄에서 인식하는 명령줄 옵션이 나와 있습니다.
  
**Office 설치 명령줄 옵션**

|**설치 명령줄 옵션**|**설명**|
|:-----|:-----|
|/admin  <br/> |Office 사용자 지정 도구를 실행하여 설치 사용자 지정 파일(.msp 파일)을 만듭니다.  <br/> |
|/adminfile [path]  <br/> |지정된 설치 사용자 지정 파일을 설치에 적용합니다. 특정 사용자 지정 파일(.msp 파일)의 경로 또는 사용자 지정 파일이 저장된 폴더의 경로를 지정할 수 있습니다.  <br/> |
|/config [path]  <br/> |설치하는 동안 설치 프로그램에서 사용할 Config.xml 파일을 지정합니다. /config 옵션을 사용하여 비즈니스용 Skype Config.xml 사용자 지정한 Config.xml 지정합니다. 예를 들면 다음과 같습니다.  `/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |수정된 Config.xml 파일과 함께 유지 관리 모드로 설치 프로그램을 실행하고 기존 Office 설치를 변경하는 데 사용됩니다. 예를 들어 /modify 옵션을 사용하여 비즈니스용 Skype 기능을 추가하거나 제거할 수 있습니다.  <br/> |
|/repair Skype  <br/> |사용자의 컴퓨터에서 설치를 실행하여 비즈니스용 Skype를 복구합니다.  <br/> |
|/uninstall Skype  <br/> |설치를 실행하여 사용자 컴퓨터에서 비즈니스용 Skype를 제거합니다.  <br/> |
   


