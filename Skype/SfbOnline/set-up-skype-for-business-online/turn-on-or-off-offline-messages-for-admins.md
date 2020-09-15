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
description: 연락처가 PowerShell을 사용 하 여 로그인 하지 않은 경우에도 비즈니스용 Skype 인스턴트 메시지를 보내는 방법에 대해 알아봅니다.
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814607"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>관리자의 오프라인 메시지 설정 또는 해제

로그인 하지 않은 경우에도 비즈니스용 Skype Im을 대화 상대에 게 보낼 수 있습니다. 이 기능을 통해 귀하의 연락처에 게 연락을 시도 하 고 있음을 알릴 수 있습니다. 메시지를 보내기 전에 다른 사람이 온라인 상태가 될 때까지 기다릴 필요가 없습니다.

오프 라인 메시지의 경우 다음 사항에 유의 해야 합니다.

- 오프 라인 메시지는 사용자의 사서함에 보관 되지 않습니다.

- 오프 라인 메시지는 사용자의 사서함으로 보내지며 사용자는 비즈니스용 Skype에 로그인 할 때 알림을 받습니다.

- 메시지 받는 사람의 상태가 방해 금지 또는 표시로 설정 **되 면 받는**사람의 비즈니스용 Skype 클라이언트에서 보낸 부재 **중** 메시지가 수신 됩니다.

자세한 내용은 [비즈니스용 Skype에서 오프 라인 메시지 사용](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)을 참조 하세요.

## <a name="to-get-you-started"></a>시작 하기

## #

 **Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**

1. 버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴**에서  >  **Windows PowerShell**을 수행 합니다.

2. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.

3. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.

4. 비즈니스용 Skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 팀 용 Windows PowerShell 모듈도 설치 해야 합니다.

자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.

## #

 **Windows PowerShell 세션 시작**

1. **시작 메뉴**에서  >  **Windows PowerShell**을 실행 합니다.

2. **Windows PowerShell** 창에서 다음을 실행 하 여 Microsoft 365 또는 Office 365에 연결 합니다.

   > [!NOTE]
   > 비즈니스용 Skype Online 커넥터는 현재 최신 팀 PowerShell 모듈의 일부입니다.
   >
   > 최신 [팀 PowerShell 공용 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/)를 사용 하 고 있는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.

## <a name="turning-on-or-off-offline-im"></a>오프 라인 메신저 대화 설정 또는 해제

> [!NOTE]
> 오프 라인 메시지는 최신 버전의 간편 실행 비즈니스용 Skype 클라이언트 **에서만** 사용할 수 있으며, 이전에 실행 중인 비즈니스용 skype를 사용 하는 경우에는 사용할 수 없으며 비즈니스용 skype 클라이언트를 설치 하는 데 * .msi 파일이 사용 되었습니다.

오프 라인 메시지를 설정 하거나 해제 하려면 조직의 사용자에 게 오프 라인 메시지를 보내려면  _EnableIMAutoArchiving_ 를 또는으로 설정 `True` `False` 합니다. 기본적으로이로 설정 됩니다 `True` .

이 기능을 해제 하려면 **Set-CsClientPolicy** cmdlet을 사용 하 여 다음을 실행 합니다.

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

오프 라인 메시지를 설정 하거나 해제 하려면 사용자에 게 오프 라인 메시지를 보내려면  _EnableIMAutoArchiving_ 를 또는으로 설정 `True` `False` 합니다. 기본적으로이로 설정 됩니다  `True` . 기존 정책을 사용 하거나 아래 예제와 같은 항목을 만들 수 있습니다.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.

  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 해야 하는 여섯 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.

  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)


