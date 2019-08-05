---
title: Windows PowerShell 및 비즈니스용 Skype 서버 관리 도구
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 비즈니스용 Skype 서버에서 관리 도구는 Windows PowerShell을 사용 하 여 구현 됩니다. Windows PowerShell에는 명령줄 환경, 제품별 명령, 전체 스크립트 언어가 포함 됩니다. Windows PowerShell을 사용 하 여 구현 된 비즈니스용 Skype 서버 도구에는 다음이 포함 됩니다.
ms.openlocfilehash: 3eb156e002603378ec77fbbcbde4772870aad907
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196833"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell 및 비즈니스용 Skype 서버 관리 도구
 
비즈니스용 Skype 서버에서 관리 도구는 Windows PowerShell을 사용 하 여 구현 됩니다. Windows PowerShell에는 명령줄 환경, 제품별 명령, 전체 스크립트 언어가 포함 됩니다. Windows PowerShell을 사용 하 여 구현 된 비즈니스용 Skype 서버 도구에는 다음이 포함 됩니다. 
  
- **토폴로지 작성기**. 토폴로지 작성기를 사용 하 여 계획 된 토폴로지를 만들고, 조정 하 고, 게시 하 고, 서버 설치를 시작 하기 전에 토폴로지의 유효성을 검사 합니다. 개별 서버에 비즈니스용 Skype 서버를 설치 하는 경우 서버는 설치 프로세스의 일부로 게시 된 토폴로지를 읽고, 설치 프로그램은 토폴로지에서 지시한 대로 서버를 배포 합니다. 설치 후에는 모든 서버에 구성 정보가 자동으로 복제 됩니다. 토폴로지 작성기를 사용 하는 경우에만 구성 요소를 배포에 추가할 수 있습니다.
    
- **비즈니스용 Skype 서버 관리 셸**. 배포의 전체 명령줄 관리에 비즈니스용 Skype Server Management Shell을 사용할 수 있습니다.
    
- **비즈니스용 Skype 서버 제어판** 비즈니스용 Skype Server 제어판 사용자 인터페이스를 사용 하 여 배포에서 가장 일반적인 작업을 관리할 수 있습니다.
    
이러한 도구는 550 제품별 cmdlet을 포함 하 여 배포 관리를 위해 Windows PowerShell cmdlet을 사용 합니다. 비즈니스용 Skype 서버용으로 제공 되는 보안 cmdlet은 주로 인증을 관리 하는 데 사용 되며 사용자 권한 및 사용 권한입니다. 인증서 및 PIN (개인 식별 번호) 인증에 대 한 cmdlet을 비롯 한 다양 한 cmdlet을 인증 관리에 사용할 수 있습니다. 또한 많은 cmdlet을 사용 하 여 새 RBAC (역할 기반 액세스 제어) 기능을 통해 비즈니스용 Skype 서버에 대 한 관리 제어권을 위임할 수 있습니다. 비즈니스용 Skype 서버 cmdlet에 대 한 자세한 내용은 비즈니스용 [Skype Server Management Shell](../../manage/management-shell.md)을 참조 하세요.
  
Windows PowerShell 용 스크립트 보안 기능은 Microsoft VBScript (Visual Basic Scripting Edition)를 포함 하 여 이전 기술의 일부 스크립팅 관련 보안 문제를 방지 하기 위해 특별히 설계 되었습니다. Windows PowerShell 보안 기능은 사용자가 스크립트를 쉽게 실행할 수 없는 환경을 만들기 위한 것입니다. 기본적으로 Windows PowerShell 보안 기능을 사용할 수 있습니다. 이러한 기능의 상태를 스크립트 요구와 다양 한 보안 목표에 맞게 수정할 수 있습니다. 이는 셸이 사용자가 스크립트를 실행할 수 없다는 것을 말합니다. 대신 셸은 기본적으로 사용자가 수행 하는 작업을 인식 하지 않고 스크립트를 실행할 수 있도록 어렵게 만듭니다. 자세한 내용은 [Windows PowerShell 스크립트 보안](https://go.microsoft.com/fwlink/p/?LinkId=213145)을 참조 하세요.
  

