---
title: 관리자의 오프라인 메시지 설정 또는 해제
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
- Setup
description: PowerShell을 사용하여 연락처에 로그인하지 않은 경우에도 비즈니스용 Skype 인스턴트 메시지를 보내는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 82b6b6c70e129d152d716cdc2567a9776b9d0302
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103824"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>관리자의 오프라인 메시지 설정 또는 해제

비즈니스용 Skype IM을 연락처에 로그인하지 않은 경우에도 보낼 수 있습니다. 이 기능을 사용하면 연락처가 연락처에 도달하려고 시도했다는 것을 알 수 있습니다. 메시지를 보내기 전에 누군가가 온라인이 될 때까지 기다릴 수 없습니다.

오프라인 메시지의 경우 다음을 알아야 합니다.

- 오프라인 메시지는 사용자의 사서함에 보관되지 않습니다.

- 오프라인 메시지는 사용자의 사서함으로 전송되고 비즈니스용 Skype에 로그인하면 사용자에게 알림을 하게 됩니다.

- 메시지 받는 사람의 상태가 방해  금지 또는 발표 금지로 설정되어 있는 경우 받는 사람의 비즈니스용 Skype 클라이언트에서 보낸 부재 중 메시지를 받게 됩니다.

자세한 내용은 [비즈니스용 Skype에서 오프라인 메시징 사용을 참조하세요.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)

## <a name="to-get-you-started"></a>시작을 위해

> [!NOTE]
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.
1. Teams [PowerShell 모듈을 설치합니다.](/microsoftteams/teams-powershell-install)
    
2. 명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다. 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
시작에 대한 자세한 Windows PowerShell 단일 창에서 모든 [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 서비스에 연결하거나 Windows PowerShell 에 대해 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>오프라인 IM 켜기 또는 끄기

> [!NOTE]
> 오프라인 **메시지는** 비즈니스용 Skype 클라이언트의 최신 버전에서만 사용할 수 있으며 이전 비즈니스용 Skype를 사용하거나 비즈니스용 Skype 클라이언트를 설치하는 데 *.msi 파일을 사용하는 경우 사용할 수 없습니다.

조직의 사용자에 대한 오프라인 메시지 보내기 오프라인 메시지를 사용하도록 설정하거나 사용하지 않도록 설정하려면  _EnableIMAutoArchiving을_ 또는 `True` `False` 으로 설정합니다. 기본적으로 이 설정은 `True` 으로 설정됩니다.

해제하기 위해 **Set-CsClientPolicy** cmdlet을 사용하여 실행합니다.

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

사용자에 대한 오프라인 메시지를 보내기 위해 오프라인 메시지를 사용하도록 설정하거나 사용하지 않도록 설정하려면  _EnableIMAutoArchiving을_ 또는 `True` `False` 으로 설정합니다. 기본적으로 이 설정은  `True` 으로 설정됩니다. 기존 정책을 사용하거나 아래 예제와 같은 정책을 만들 수 있습니다.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.

  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Microsoft 365 또는 Office 365를 Windows PowerShell 사용하려는 6 가지 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.

  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [비즈니스용 skype Windows PowerShell 관리하기 위해 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)