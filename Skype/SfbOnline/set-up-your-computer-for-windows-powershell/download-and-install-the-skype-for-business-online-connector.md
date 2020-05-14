---
title: 비즈니스용 Skype Online 커넥터 모듈 다운로드 및 설치
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: '비즈니스용 skype online 커넥터를 다운로드 하 여 설치 하 고 사용 하 여 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만듭니다. '
ms.openlocfilehash: 14e45765c4f1102242efe93548096dabf0174ff7
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224111"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>비즈니스용 Skype Online 커넥터 모듈 다운로드 및 설치

비즈니스용 Skype Online 커넥터 모듈에는 비즈니스용 Skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 **새로운 CsOnlineSession** cmdlet이 포함 되어 있습니다. 64 비트 컴퓨터 에서만 지원 되는이 모듈 (자세한 내용은 [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리를 위해 컴퓨터 설정](set-up-your-computer-for-windows-powershell.md) 참조)을 Microsoft 다운로드 센터에서 다운로드할 수 있습니다 [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) . SkypeOnlinePowershell 파일을 다운로드 하 고 다음 절차를 완료 합니다.
  
1. **SkypeOnlinePowershell** 파일을 두 번 클릭 합니다.
    
2. 비즈니스용 Skype Online, Windows PowerShell 설치 마법사의 **Microsoft 소프트웨어 사용 조건** 페이지에서 **사용권 계약에 동의 함을**선택 하 고 **설치**를 클릭 합니다. **사용자 계정 컨트롤** 대화 상자가 표시 되는 경우 **예** 를 클릭 하 여 설치를 계속 합니다.
    
3. 완료 된 비즈니스용 **Skype Online, Windows PowerShell 모듈** 페이지에서 **마침을**클릭 합니다.
    
설치 프로그램이 비즈니스용 Skype Online 커넥터 모듈 (및 **CsOnlineSession** cmdlet)을 컴퓨터에 복사 합니다. 모듈에 액세스 하려면 관리자 자격 증명에서 Windows PowerShell 세션을 시작 하 고 다음 명령을 실행 합니다.
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

Windows PowerShell을 시작할 때마다이 명령을 입력 하지 않으려면 Windows PowerShell 프로필에 명령을 추가 하면 됩니다. 이렇게 하려면 Windows PowerShell 프롬프트에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
  
```PowerShell
notepad.exe $profile
```

 메모장이 나타나면 프로필에 이미 있는 명령의 아래쪽에 다음 줄을 추가 합니다 (있는 경우).
  
```PowerShell
Import-Module SkypeOnlineConnector
```

파일을 저장 합니다. 다음에 Windows PowerShell을 시작할 때 비즈니스용 Skype Online 커넥터 모듈을 자동으로 가져옵니다. 관리자 자격 증명으로 Windows PowerShell을 실행 하지 않는 경우에는 오류 메시지가 표시 되 고 모듈이 로드 되지 않을 수 있다는 점에 주의 하세요.
  
SkypeOnlinePowershell는 비즈니스용 Skype Online Connector 모듈을 설치 하는 것 외에도 3 개의 추가 구성 요소 (1)를 사용 하 여 비즈니스용 Skype Online에 대 한 클라이언트 인증을 처리 하는 IDCRL (Id 서비스 클라이언트 런타임 라이브러리)를 설치 합니다. 2) .NET Framework 4.5; and, 3) Microsoft Visual c + + 2012 재배포 가능 (x64) 패키지 (버전 11.0.50727). .NET Framework 4.5는 Windows PowerShell을 포함 하 여 .NET 응용 프로그램을 빌드 및 실행 하는 데 사용 되는 인프라를 제공 합니다. Visual c + + 재배포 가능 패키지는 Microsoft Visual Studio 2012이 설치 되어 있지 않은 컴퓨터의 Visual c + + 런타임 구성 요소를 설치 합니다.
  
컴퓨터에 현재 설치 되어 있는 커넥터 모듈의 버전 번호를 확인 하려면 제어판을 열고 **프로그램 및 기능**을 연 다음 비즈니스용 **Skype Online, Windows PowerShell 모듈**의 버전 번호를 확인 합니다.
  
## <a name="related-topics"></a>관련 항목
[Windows PowerShell을 사용 하 여 비즈니스용 skype online 관리를 위한 컴퓨터 설정](set-up-your-computer-for-windows-powershell.md)

  
 
