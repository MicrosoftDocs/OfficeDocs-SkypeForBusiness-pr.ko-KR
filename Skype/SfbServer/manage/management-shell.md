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
description: 비즈니스용 Skype 서버 관리 셸은 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공합니다. 이 cmdlet은 Windows PowerShell 및 레거시 Lync 서버 제품과 관련한 포괄적인 관리 및 관리 cmdlet 집합을 Skype 포함합니다.
ms.openlocfilehash: 7213941b6f664375a6c51c3decb3080321e916d231fea3d93e5a933e4f0281f1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313146"
---
# <a name="skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 쉘
 
비즈니스용 Skype 서버 관리 셸은 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공합니다. 이 cmdlet은 Windows PowerShell 및 레거시 Lync 서버 제품과 관련한 포괄적인 관리 및 관리 cmdlet 집합을 Skype 포함합니다.
  
Windows PowerShell 명령줄에서 Microsoft 응용 프로그램을 관리할 수 있습니다. 여기에는 명령줄 환경, 제품별 명령 및 전체 스크립팅 언어가 포함됩니다. Windows PowerShell 2006년 후반에 Windows 운영 체제를 위한 다운로드 가능한 릴리스로 처음 도입되어 2007년 2007의 관리성을 위한 명령줄 인터페이스로 Microsoft Exchange Server 있습니다. Lync Server 2010부터는 Lync 및 Skype 서버 등 대부분의 Microsoft Server 제품에 통합되어 있습니다. Lync 관리 셸에서 700개 Skype 특정 cmdlet을 사용할 비즈니스용 Skype 서버 있습니다.
  
> [!NOTE]
> 비즈니스용 Skype cmdlet 참조가 docs.microsoft.com. 아래 링크를 클릭하면 새 페이지로 docs.microsoft.com 있습니다. 이제 콘텐츠가 오픈 소스로 제공되어 커뮤니티를 통해 커뮤니티에 GitHub. 기여에 관심이 있나요? 리포지타임에서 README를 확인한 다음을 확인할 수 있습니다. [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
비즈니스용 Skype 서버 700개가 넘는 cmdlet이 함께 발송되어 관리자가 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버 수 있습니다. 다음과 같은 명령을 입력하여 명령줄에서 직접 cmdlet에 대한 도움말을 검색할 수 있습니다.
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

위의 명령은 **New-CsVoicePolicy** cmdlet에 사용할 수 있는 전체 도움말을 검색합니다. 다른 cmdlet에 대한 도움말을 보기 위해 **New-CsVoicePolicy를** 도움말을 검색할 cmdlet 이름으로 대체합니다.
  
cmdlet을 관리하는 데 사용할 수 있는 전체 cmdlet 목록을 비즈니스용 Skype 서버 셸 명령 프롬프트에 다음을 입력합니다. 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



다음을 통해 Windows PowerShell 알아야 비즈니스용 Skype 서버.
  
- cmdlet을 비즈니스용 Skype 서버 관리 셸을 비즈니스용 Skype 서버 를 런타입니다.
    
    > [!CAUTION]
    > Windows PowerShell 관리 셸이 비즈니스용 Skype 서버 창을 여는 경우 기본적으로 Skype cmdlet을 실행하지 않을 수 있습니다. 비즈니스용 Skype 서버 cmdlet을 Windows PowerShell 명령 프롬프트에 다음을 Windows PowerShell 입력합니다. >`Import-Module SkypeforBusiness`
  
- 비즈니스용 Skype 서버 관리 셸은 모든 프런트 엔드 서버 또는 비즈니스용 Skype 서버 Enterprise Edition 서버에 자동으로 Standard Edition 설치됩니다.
    
- [Update-Help](/powershell/module/microsoft.powershell.core/update-help) cmdlet을 비즈니스용 Skype 서버 관리 셸 도움말 콘텐츠를 업데이트할 수 있습니다. 이 Update-Help cmdlet은 컴퓨터에 설치된 모든 모듈에 사용할 수 있는 최신 도움말 파일을 다운로드하여 설치합니다(cmdlet에 대한 비즈니스용 Skype 포함).
    
    기본적으로 **Update-Help** cmdlet은 사용자 컴퓨터에 설치된 모든 모듈을 비즈니스용 Skype 서버. 특정 모듈만 업데이트하려는 경우 _Module_ 매개 변수를 사용하여 cmdlet의 범위를 제한할 수 있습니다. 다음은 새 모듈만 비즈니스용 Skype 예제입니다.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    인터넷에 연결되지 않은 서버에서 도움말을 업데이트해야 하는 경우 [Save-Help](/powershell/module/microsoft.powershell.core/save-help) cmdlet을 사용하여 도움말의 최신 버전을 다운로드하고 지정한 위치에 저장할 수 있습니다. 그런 다음 인터넷에 연결되지 않은 서버에서 **Update-Help** cmdlet을 _-SourcePath_ 매개 변수와 함께 사용하여 선택한 위치에서 업데이트된 도움말을 얻을 수 있습니다. 다음 예제에서는 도움말 파일을 네트워크 파일 공유에 저장한 다음 파일 공유에서 비즈니스용 Skype 모듈에 대한 도움말을 업데이트하는 방법을 보여줍니다.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    자세한 내용은 [Updatable 도움말 정보를 참조하세요.](/powershell/module/microsoft.powershell.core/about/about_updatable_help)
    
    > [!NOTE]
    > 원격으로 PowerShell을 사용하는 경우 방화벽을 통한 통신을 허용해야 할 수 있습니다. PowerShell에서 사용하는 포트에 대한 자세한 내용은 [PowerShell Remoting Use?를 참조하세요.](/archive/blogs/christwe/what-port-does-powershell-remoting-use)
