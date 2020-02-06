---
title: 비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM) 사용 또는 사용 안 함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM)를 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d96c7fc0de51cbdcfb6ba3acde3bf854c874f05b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795329"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM) 사용 또는 사용 안 함
 
비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM)를 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM) 사용

오프 라인 IM은 비즈니스용 skype 클라이언트 (2016 C2R 빌드 16.0.6701.1000 이상)에 기본으로 제공 되는 클라이언트측 기능으로, EWS (Exchange Web Services)를 사용 하 여 사용자의 Exchange 사서함으로 메시지를 보낼 수 있습니다. 오프 라인 IM은 비즈니스용 Skype 클라이언트에서 받는 사람 사서함으로 오프 라인 메시지를 보내는 데 사용 됩니다 (Exchange Web Services (EWS)). EWS는 비즈니스용 Skype 클라이언트에서 오프 라인 메시지를 보내기 위해 사용할 수 있어야 합니다. 인스턴트 메시지 및 현재 상태에 대 한 계획 수립에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 인스턴트 메시지 및 현재 상태에 대 한 계획](../../plan-your-deployment/instant-messaging-and-presence.md)을 참조 하세요.
  
> [!NOTE]
> 사용자의 사서함이 Exchange 온-프레미스에 호스팅되는 경우 비즈니스용 Skype 클라이언트 (2016 C2R build 16.0.6920.1000)가 필요 합니다. 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 오프 라인 메신저 기능을 사용 하거나 사용 하지 않도록 설정 하려면

1. 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 다음 명령을 실행 하 여 오프 라인 IM을 사용 하도록 설정 합니다.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 비즈니스용 Skype Server 2015 CU3 이상의 EnableOfflineIM 옵션은 기본적으로 $True으로 설정 됩니다. 사용 하지 않으려면이 값을 $False로 설정 합니다. 
  
3. 다음 명령을 실행 하 여 오프 라인 메신저 대화를 저장 하는 기능이 설정 되었는지 확인 합니다.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Exchange와의 오프 라인 IM 통합

대화 내용 폴더에 오프 라인 메시지 자동 저장을 사용 하지 않도록 설정 하는 클라이언트 정책이 있는 경우 보낸 사람에 게 오프 라인 IM을 사용할 수 없습니다 (EnableIMAutoArchiving = $false). 받는 사람이 오프 라인 메시지를 받을 수 있는지 확인 하는 메커니즘은 없습니다.
  
동일한 조직 내에서 보낸 오프 라인 메시지의 경우 IM의 메시지 클래스를 사용 하 여 전자 메일 메시지로 수신 됩니다. 참고. 대화는 Outlook **부재 중 대화** 폴더에 포함 되며, 비즈니스용 Skype 클라이언트의 최근 목록/대화 내용 탭에서 선택 되는 대화 내용입니다.
  
페더레이션 조직에서 보낸 오프 라인 메시지의 경우 IM을 사용 하지 않고 전자 메일 메시지로 수신 됩니다. MisssedConversation는 부재 중 대화 또는 대화 내용 폴더에 선택 되지 않습니다. 
  
## <a name="troubleshooting"></a>해결사

오프 라인 메시지를 선택 하 고 처리 하는 경우에는 2 분 타이머가 있습니다. 오프 라인 메시지를 처리할 수 없는 경우 다음 디렉터리에 표시 됩니다. 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

기본 비즈니스용 Skype ETL 로그에는 오프 라인 메시지 처리에 대 한 정보가 포함 되며 조사/문제 해결을 위한 가장 좋은 원본입니다. 
  
> [!NOTE]
> 오프 라인 메시지를 보낼 수 없고 ' 임시 보관 함 ' 폴더가 메시지로 채워져 있는 동안 문제가 보고 되었습니다. Exchange 온-프레미스 사서함에서 발생 했습니다. 6/14/2016의 모든 C2R 채널에서 문제가 해결 되었습니다.  
