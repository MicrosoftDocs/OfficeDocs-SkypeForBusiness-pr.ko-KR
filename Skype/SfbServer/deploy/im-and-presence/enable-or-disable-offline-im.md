---
title: 모바일 기능에서 오프라인 IM(인스턴트 메시징)을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 모바일 기능에서 오프라인 IM(인스턴트 메시징)을 사용하도록 설정하거나 사용하지 않도록 설정하는 비즈니스용 Skype 서버.
ms.openlocfilehash: 36894fb2a1ed11428b21b572a28e9ac177a4237d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753330"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>모바일 기능에서 오프라인 IM(인스턴트 메시징)을 비즈니스용 Skype 서버
 
모바일 기능에서 오프라인 IM(인스턴트 메시징)을 사용하도록 설정하거나 사용하지 않도록 설정하는 비즈니스용 Skype 서버.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>모바일 기능에서 오프라인 IM(인스턴트 메시징)비즈니스용 Skype 서버

오프라인 IM은 EWS(Exchange Web Services)를 활용하여 비즈니스용 Skype 클라이언트에서 사용자의 Exchange 사서함으로 메시지를 보내는 비즈니스용 Skype 클라이언트(2016 C2R 빌드 16.0.6701.1000 이상)에 기본 제공되는 클라이언트 쪽 기능입니다. 오프라인 IM은 Exchange 웹 서비스(EWS)를 사용하여 비즈니스용 Skype 클라이언트에서 받는 사람의 사서함으로 오프라인 메시지를 보냅니다. 오프라인 메시지를 보내기 위해 비즈니스용 Skype 클라이언트에서 EWS를 사용할 수 있어야 합니다. 인스턴트 메시징 및 현재 상태 계획에 대한 자세한 내용은 [Plan for instant messaging and presence in 비즈니스용 Skype 서버.](../../plan-your-deployment/instant-messaging-and-presence.md)
  
> [!NOTE]
> 사용자의 사서함이 Exchange 비즈니스용 Skype 클라이언트(2016 C2R 빌드 16.0.6920.1000)가 필요합니다. 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>오프라인 IM을 사용하도록 설정하거나 사용하지 않도록 비즈니스용 Skype 서버

1. 관리 비즈니스용 Skype 서버 셸을 열 수 있습니다.
    
2. 다음 명령을 실행하여 오프라인 IM을 사용하도록 설정할 수 있습니다.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 비즈니스용 Skype 서버 2015 CU3에서 EnableOfflineIM 옵션은 기본적으로 $True 설정되어 있습니다. 사용하지 않도록 설정하기 위해 이 값을 $False. 
  
3. 다음 명령을 실행하여 오프라인 IM을 저장할 수 있는 설정이 설정되어 있는지 확인합니다.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>오프라인 IM과 Exchange

오프라인 메시지를 대화 기록 폴더에 자동 저장하지 않도록 설정하는 클라이언트 정책이 있는 경우 보낸 사람이 오프라인 IM을 사용할 수 없습니다(EnableIMAutoArchiving = $false). 받는 사람이 오프라인 메시지를 받을 수 있는지 확인할 수 있는 메커니즘은 없습니다.
  
동일한 조직 내에서 전송된 오프라인 메시지의 경우 메시지 클래스가 IM.Note.MissedConversation인 전자 메일 메시지로  수신되고 Outlook 부재 중 대화 폴더 및 비즈니스용 Skype 클라이언트의 최근 목록/대화 기록 탭에서 선택되는 대화 기록에 포함됩니다.
  
페더러드 조직에서 보낸 오프라인 메시지의 경우 IM.Note.MisssedConversation이 없는 전자 메일 메시지로 수신됩니다. 부재 중 대화 또는 대화 기록 폴더에서 선택되지 않습니다. 
  
## <a name="troubleshooting"></a>문제 해결

오프라인 메시지가 선택 및 처리된 경우부터 2분의 시간이 있습니다. 오프라인 메시지를 처리하지 못하면 다음 디렉터리에 표시됩니다. 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

ETL 비즈니스용 Skype 기본 메시지는 오프라인 메시지 처리에 대한 정보를 포함하며 조사/문제 해결을 위한 최상의 소스입니다. 
  
> [!NOTE]
> 오프라인 메시지가 보내지 못하고 '임시 저장' 폴더에 메시지가 채워지고 있는 문제가 보고되었습니다. 이 경우 Exchange 사서함에서 발생했습니다. The issue has been fixed in all C2R channels as of 6/14/2016.  
