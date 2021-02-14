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
description: PowerShell을 사용하여 연락처에 로그인하지 않은 경우에도 비즈니스용 Skype 인스턴트 메시지를 보내는 방법을 배워야 합니다.
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814607"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>관리자의 오프라인 메시지 설정 또는 해제

로그인하지 않은 경우에도 연락처에 비즈니스용 Skype IM을 보낼 수 있습니다. 이 기능을 통해 연락처가 연락을 시도한 것을 알 수 있습니다. 다른 사람이 온라인이 될 때까지 기다렸다가 메시지를 보내지 않습니다.

오프라인 메시지의 경우 다음을 알아야 합니다.

- 오프라인 메시지는 사용자의 사서함에 보관되지 않습니다.

- 오프라인 메시지는 사용자의 사서함으로 전송되고 비즈니스용 Skype에 로그인하면 사용자에게 통보됩니다.

- 메시지 받는 사람의 상태가 방해  금지 또는 발표 금지로 설정된 경우 받는 사람의 비즈니스용 Skype 클라이언트에서 보낸 부재 중 메시지를 받게 됩니다.

자세한 내용은 비즈니스용 [Skype에서 오프라인 메시지 사용을 참조하세요.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)

## <a name="to-get-you-started"></a>시작

## #

 **버전 3.0 Windows PowerShell 실행 중인지 확인**

1. 버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.

2. 웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인

3. 버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell. 버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다. 메시지가 표시될 때 컴퓨터를 다시 시작합니다.

4. 또한 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 Teams용 Windows PowerShell 모듈을 설치해야 합니다.

자세한 내용은 단일 365 창에서 모든 [Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)

## #

 **세션 Windows PowerShell 시작**

1. 시작 **메뉴에서**  >  **Windows PowerShell.**

2. 다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.

   > [!NOTE]
   > 비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.
   >
   > 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는 Windows PowerShell 컴퓨터를 설정하여 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>오프라인 IM 켜기 또는 끄기

> [!NOTE]
> 오프라인 **메시지는** 비즈니스용 Skype 클라이언트의 최신 버전에서만 사용할 수 있으며, 이전의 비즈니스용 Click-to-Run Skype를 사용 중이거나 비즈니스용 Skype 클라이언트를 설치하는 데 *.msi 파일을 사용한 경우 사용할 수 없습니다.

조직의 사용자에 대해 오프라인 메시지 보내기 사용 또는 사용 안 하도록 설정하려면 _EnableIMAutoArchiving을_ `True` 설정하거나 `False` 기본적으로 이 설정은 `True` .로 설정됩니다.

끄기 위해 **Set-CsClientPolicy** cmdlet을 사용하여 다음을 실행합니다.

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

사용자에 대해 오프라인 메시지 보내기 사용 또는 사용 안 하도록 설정하려면 _EnableIMAutoArchiving을_ `True` 설정하거나 `False` 기본적으로 이 설정은  `True` .로 설정됩니다. 기존 정책을 사용하거나 아래 예제와 같은 정책을 만들 수 있습니다.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 내용은 Windows PowerShell?

- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.

  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Microsoft 365 또는 Office 365를 관리하기 위해 Windows PowerShell 사용할 수 있는 6 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.

  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)


