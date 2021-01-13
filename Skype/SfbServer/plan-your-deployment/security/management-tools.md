---
title: Windows PowerShell 및 비즈니스용 Skype 서버 관리 도구
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 비즈니스용 Skype 서버에서는 관리 도구를 사용하여 Windows PowerShell. Windows PowerShell에는 명령줄 환경, 제품별 명령 및 전체 스크립팅 언어가 포함됩니다. 비즈니스용 Skype 서버 도구를 사용하여 구현되는 Windows PowerShell 다음이 포함됩니다.
ms.openlocfilehash: 740a5e3d7998523970e1b0adc1e72aa85d0b09c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832158"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell 및 비즈니스용 Skype 서버 관리 도구
 
비즈니스용 Skype 서버에서는 관리 도구를 사용하여 Windows PowerShell. Windows PowerShell에는 명령줄 환경, 제품별 명령 및 전체 스크립팅 언어가 포함됩니다. 비즈니스용 Skype 서버 도구를 사용하여 구현되는 Windows PowerShell 다음이 포함됩니다. 
  
- **토폴로지 작성기.** 토폴로지 작성기에서 계획한 토폴로지 작성, 조정 및 게시를 진행하고 서버 설치를 시작하기 전에 토폴로지의 유효성을 검사합니다. 개별 서버에 비즈니스용 Skype 서버를 설치하면 서버가 설치 프로세스의 일부로 게시된 토폴로지의 내용을 읽고 설치 프로그램에서 토폴로지의 지시에 따라 서버를 배포합니다. 설치 후에는 구성 정보가 모든 서버에 자동으로 복제됩니다. 구성 요소는 토폴로지 작성기만 사용하여 배포에 추가할 수 있습니다.
    
- **비즈니스용 Skype 서버 관리 셸.** 비즈니스용 Skype 서버 관리 셸을 사용하여 배포의 전체 명령줄 관리를 할 수 있습니다.
    
- **비즈니스용 Skype 서버 제어판.** 비즈니스용 Skype 서버 제어판 사용자 인터페이스를 사용하여 배포에서 가장 일반적인 작업을 관리할 수 있습니다.
    
이러한 도구에서는 약 550개의 제품별 cmdlet을 포함하여 배포 관리를 위한 Windows PowerShell cmdlet이 사용됩니다. 비즈니스용 Skype 서버에 포함된 보안 cmdlet은 주로 인증 및 사용자 권한 및 사용 권한을 관리하는 데 사용됩니다. 인증서 및 PIN(개인 식별 번호) 인증을 위한 cmdlet 등 인증 관리에 사용할 수 있는 다양한 cmdlet가 있습니다. 또한 다양한 cmdlet을 사용하여 새로운 RBAC(Role-Based 액세스 제어) 기능을 사용하여 비즈니스용 Skype 서버의 관리 제어를 위임할 수 있습니다. 비즈니스용 Skype 서버 cmdlet에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../../manage/management-shell.md)
  
Windows PowerShell의 스크립트 보안 기능은 특히 Microsoft Visual Basic Scripting Edition(VBScript)을 포함하는 이전 기술들의 일부 스크립트 관련 보안 문제를 방지하도록 설계되었습니다. Windows PowerShell 보안 기능은 사용자가 쉽게 또는 알지 못한 상태로 스크립트를 실행할 수 없는 환경을 만들기 위한 것입니다. Windows PowerShell 보안 기능은 기본적으로 활성화되어 있습니다. 스크립트 요구 사항 및 다양한 보안 목표에 맞게 이러한 기능의 상태를 수정할 수 있습니다. 그렇다고 해서 사용자가 스크립트를 실행할 수 없도록 하는 것은 아닙니다. 셸의 목적은 사용자가 자신이 스크립트를 실행하고 있다는 사실을 인지하지 못한 상태로 스크립트를 실행하기 어렵게 만들기 위한 것입니다. 자세한 내용은 [Windows PowerShell Script Security를 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=213145)
  

