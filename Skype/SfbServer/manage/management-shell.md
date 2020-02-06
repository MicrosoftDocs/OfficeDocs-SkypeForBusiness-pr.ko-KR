---
title: 비즈니스용 Skype 서버 관리 셸
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 비즈니스용 Skype 서버 관리 셸에서는 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공 합니다. 이 파일은 Windows PowerShell을 기반으로 하며, Skype 및 레거시 Lync server 제품과 관련 된 포괄적인 관리 및 관리 cmdlet 집합을 포함 합니다.
ms.openlocfilehash: 294de750795985d50c6301a88f4b835f1cad78b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817557"
---
# <a name="skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸
 
비즈니스용 Skype 서버 관리 셸에서는 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공 합니다. 이 파일은 Windows PowerShell을 기반으로 하며, Skype 및 레거시 Lync server 제품과 관련 된 포괄적인 관리 및 관리 cmdlet 집합을 포함 합니다.
  
Windows PowerShell을 사용 하면 명령줄에서 Microsoft 응용 프로그램을 관리할 수 있습니다. 여기에는 명령줄 환경, 제품별 명령, 전체 스크립팅 언어가 포함됩니다. Windows PowerShell은 먼저 2006에서 발생 하는 Windows 운영 체제의 다운로드 가능한 릴리스로 도입 되었으며 Microsoft Exchange Server 2007의 관리 효율성을 위한 명령줄 인터페이스로 통합 되었습니다. Lync 서버 2010으로 시작 하는 Lync 및 Skype 서버를 포함 하 여 대부분의 Microsoft 서버 제품에 통합 되어 있습니다. 비즈니스용 Skype 서버 관리 셸에서 사용할 수 있는 700 Lync 및 Skype 관련 cmdlet이 있습니다.
  
> [!NOTE]
> 비즈니스용 Skype cmdlet 참조가 docs.microsoft.com으로 이동 했습니다. 아래 링크를 클릭 하면 새 docs.microsoft.com 페이지로 이동 합니다. 이제 콘텐츠가 열리고, GitHub를 통해 커뮤니티에서 기고 가능 합니다. 참여 하는 데 관심이 있으십니까? 여기에 있는 리포지토리의 추가 정보를 확인 하세요.[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
비즈니스용 skype Server에는 관리자가 비즈니스용 skype 서버 관리 셸을 사용 하 여 비즈니스용 Skype 서버를 관리할 수 있는 700 cmdlet이 포함 되어 있습니다. 다음과 같은 명령을 입력 하 여 명령줄에서 직접 cmdlet에 대 한 도움말을 검색할 수 있습니다.
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

앞의 명령은 **새 CsVoicePolicy** cmdlet에 대해 사용할 수 있는 전체 도움말을 검색 합니다. 다른 cmdlet에 대 한 도움말을 보려면 도움말을 검색 하려는 cmdlet의 이름으로 **CsVoicePolicy** 를 대체 합니다.
  
비즈니스용 Skype 서버를 관리 하는 데 사용할 수 있는 전체 cmdlet 목록을 검색 하려면 shell 명령 프롬프트에 다음을 입력 합니다. 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



비즈니스용 Skype 서버에서 Windows PowerShell에 대해 알아야 할 사항:
  
- 비즈니스용 Skype 서버 cmdlet을 실행 하려면 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
    > [!CAUTION]
    > 비즈니스용 Skype 서버 관리 셸이 아닌 Windows PowerShell 창을 열면 기본적으로 Skype cmdlet을 실행 하지 못할 수 있습니다. Windows PowerShell에서 비즈니스용 Skype Server cmdlet을 실행 하려면 먼저 Windows PowerShell 명령 프롬프트에 다음을 입력 합니다. >`Import-Module SkypeforBusiness`
  
- 비즈니스용 skype 서버 관리 셸이 모든 비즈니스용 Skype Server Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치 됩니다.
    
- [업데이트 도움말](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet을 실행 하 여 비즈니스용 Skype 서버 관리 셸 도움말 콘텐츠를 업데이트할 수 있습니다. 업데이트 도움말 cmdlet은 비즈니스용 Skype cmdlet에 대 한 업데이트를 포함 하 여 컴퓨터에 설치 된 모든 모듈에 사용할 수 있는 최신 도움말 파일을 다운로드 하 고 설치 합니다.
    
    기본적으로 **업데이트 도움말** Cmdlet은 비즈니스용 Skype 서버에 설치 된 모든 모듈을 업데이트 합니다. 특정 모듈만 업데이트하려면 _Module_ 매개 변수를 사용해 cmdlet의 범위를 제한할 수 있습니다. 다음 예에서는 비즈니스용 Skype 모듈만 업데이트 합니다.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    인터넷에 연결 되어 있지 않은 서버에서 도움말을 업데이트 해야 하는 경우에는 도움말 [저장](https://technet.microsoft.com/en-us/library/hh849724.aspx) 을 사용 하 여 최신 버전의 도움말을 다운로드 하 여 지정한 위치에 저장할 수 있습니다. 그러면 인터넷에 연결 되지 않은 서버의 _-SourcePath_ 매개 변수를 사용 하 여 **업데이트** 된 도움말을 선택한 위치에서 가져올 수 있습니다. 다음 예제에서는 도움말 파일을 네트워크 파일 공유에 저장 하 고 파일 공유에서 비즈니스용 Skype 모듈에 대 한 도움말을 업데이트 하는 방법을 보여 줍니다.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    자세한 내용은 업데이트할 수 있는 [도움말](https://technet.microsoft.com/library/hh847735.aspx)정보를 참조 하세요.
    
    > [!NOTE]
    > PowerShell을 원격으로 사용 하는 경우 방화벽을 통한 통신을 허용 해야 할 수 있습니다. PowerShell remoting이 사용 하는 포트에 대 한 자세한 내용은 [Powershell remoting에 사용](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)되는 포트에 대해 자세히 알아보세요.
    

