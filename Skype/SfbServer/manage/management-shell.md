---
title: 비즈니스용 Skype 서버 관리 쉘
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 비즈니스용 Skype 서버 관리 셸은 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공합니다. 이 Cmdlet은 Windows PowerShell Skype 및 레거시 Lync 서버 제품과 관련이 있는 포괄적인 관리 및 관리 cmdlet 집합을 포함합니다.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816538"
---
# <a name="skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 쉘
 
비즈니스용 Skype 서버 관리 셸은 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공합니다. 이 Cmdlet은 Windows PowerShell Skype 및 레거시 Lync 서버 제품과 관련이 있는 포괄적인 관리 및 관리 cmdlet 집합을 포함합니다.
  
Windows PowerShell 명령줄에서 Microsoft 응용 프로그램을 관리할 수 있습니다. 여기에는 명령줄 환경, 제품별 명령 및 전체 스크립팅 언어가 포함됩니다. Windows PowerShell 2006년 후반 Windows 운영 체제용 다운로드 가능 릴리스로 처음 도입되어 2007년 2007의 관리 기능을 위한 명령줄 인터페이스로 Microsoft Exchange Server 있습니다. Lync Server 2010부터는 Lync 및 Skype 서버를 포함하여 대부분의 Microsoft Server 제품에 통합됩니다. 비즈니스용 Skype 서버 관리 셸에서 700개가 넘는 Lync 및 Skype 관련 cmdlet을 사용할 수 있습니다.
  
> [!NOTE]
> 비즈니스용 Skype cmdlet 참조가 docs.microsoft.com. 아래 링크를 클릭하면 새 웹 페이지로 docs.microsoft.com 있습니다. 이제 콘텐츠가 원본으로 제공된 후 GitHub를 통해 커뮤니티 기여에 사용할 수 있습니다. 참여에 관심이 있나요? 리포지타임에서 README를 확인한 후 다음을 확인할 수 있습니다. [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
비즈니스용 Skype 서버는 관리자가 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버를 관리할 수 있도록 하는 700개가 넘는 cmdlet을 제공합니다. 다음과 같은 명령을 입력하여 명령줄에서 직접 cmdlet에 대한 도움말을 검색할 수 있습니다.
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

위의 명령은 **New-CsVoicePolicy** cmdlet에 사용할 수 있는 전체 도움말을 검색합니다. 다른 cmdlet에 대한 도움말을 보기 위해 **New-CsVoicePolicy를** 도움말을 검색할 cmdlet 이름으로 대체합니다.
  
비즈니스용 Skype 서버를 관리하는 데 사용할 수 있는 cmdlet의 전체 목록을 검색하기 위해 셸 명령 프롬프트에 다음을 입력합니다. 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



비즈니스용 Skype 서버에서 Windows PowerShell 알아야 할 사항:
  
- 비즈니스용 Skype 서버 cmdlet을 실행하기 위해 비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.
    
    > [!CAUTION]
    > 비즈니스용 Skype Windows PowerShell 창을 여는 경우 기본적으로 Skype cmdlet을 실행하지 않을 수 있습니다. 비즈니스용 Skype 서버 cmdlet을 Windows PowerShell 먼저 Windows PowerShell 명령 프롬프트에 다음을 입력합니다. >  `Import-Module SkypeforBusiness`
  
- 비즈니스용 Skype 서버 관리 셸은 모든 비즈니스용 Skype 서버 Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치됩니다.
    
- [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet을 실행하여 비즈니스용 Skype 서버 관리 셸 도움말 콘텐츠를 업데이트할 수 있습니다. 이 Update-Help cmdlet은 비즈니스용 Skype cmdlet에 대한 업데이트를 포함하여 컴퓨터에 설치된 모든 모듈에 사용할 수 있는 최신 도움말 파일을 다운로드하여 설치합니다.
    
    기본적으로 **Update-Help** cmdlet은 비즈니스용 Skype 서버에 설치된 모든 모듈을 업데이트합니다. 특정 모듈만 업데이트하려는 경우 _Module_ 매개 변수를 사용하여 cmdlet의 범위를 제한할 수 있습니다. 다음 예제에서는 비즈니스용 Skype 모듈만 업데이트합니다.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    인터넷에 연결되지 않은 서버에서 도움말을 업데이트해야 하는 경우 [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet을 사용하여 도움말의 최신 버전을 다운로드하고 지정한 위치에 저장할 수 있습니다. 그런 다음 인터넷에 연결되지 않은 서버에서 _-SourcePath_ 매개 변수와 함께 **Update-Help** cmdlet을 사용하여 선택한 위치에서 업데이트된 도움말을 얻을 수 있습니다. 다음 예제에서는 도움말 파일을 네트워크 파일 공유에 저장한 다음 파일 공유에서 비즈니스용 Skype 모듈에 대한 도움말을 업데이트하는 방법을 보여 제공합니다.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    자세한 내용은 [Updatable 도움말을 참조하십시오.](https://technet.microsoft.com/library/hh847735.aspx)
    
    > [!NOTE]
    > PowerShell을 원격으로 사용하는 경우 방화벽을 통한 통신을 허용해야 할 수 있습니다. PowerShell 리모팅에서 사용하는 포트에 대한 자세한 내용은 [PowerShell Remoting Use?를 참조하세요.](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)
    

