---
title: Exchange 통합 메시징 및 호스트형 음성 사서함 관리
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
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
description: PowerShell을 사용 하 여 비즈니스용 Skype Online에서 자동 전화 교환 및 구독자 액세스와 같은 Exchange 통합 메시징 기능을 관리 하 고 호스팅되는 보이스 메일을 제공 합니다.
ms.openlocfilehash: d0c2ff8cad705a2d00685e2c6935616ab8d64ac9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692683"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Exchange 통합 메시징 및 호스트형 음성 사서함 관리

Cmdlet 집합을 사용 하 여 비즈니스용 Skype Online에서 Exchange 통합 메시징 및 호스팅 보이스 메일을 관리할 수 있습니다.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Exchange 통합 메시징 및 호스팅 음성 메일 관리

다음 cmdlet을 사용 하 여 Exchange UM (통합 메시징) 및 호스팅된 보이스 메일 정책을 관리할 수 있습니다.
  

| **은**                                                                                                                                                                                                                                                                                                                        | **설명**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-C(Um연락처)](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [신규-C또는 Um연락처](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[제거-C간 Umcontact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-C간 Umcontact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Exchange UM이 호스팅된 서비스인 경우 자동 전화 교환 및 구독자 액세스 서비스에 사용 되는 연락처 개체를 만들고 관리 합니다.  <br/><br/> 비즈니스용 Skype Online은 Exchange UM을 사용 하 여 자동 전화 교환 및 구독자 액세스를 비롯 한 다양 한 음성 관련 기능을 제공 합니다. 자동 전화 교환은 전화를 자동으로 응답 하 고 올바른 사람에 게 라우팅하는 방법을 제공 합니다. 구독자 액세스를 통해 사용자는 Exchange UM에 연결 하 고 전자 메일, 음성 메시지, 연락처 및 일정 정보를 검색할 수 있습니다.  <br/><br/> Exchange UM을 호스팅 서비스로 제공 하는 경우 자동 전화 교환 및 구독자 액세스 서비스에 사용 되는 연락처 개체는 Microsoft PowerShell을 사용 하 여 만들어야 합니다. 이러한 개체는 **Csexumcontact** cmdlet을 사용 하 여 만들고 관리 합니다. <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[부여-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | 조직에서 사용 되는 호스팅된 보이스 메일 정책을 관리 합니다. 호스팅된 음성 메일 정책은 응답 하지 않은 통화가 Exchange UM 서비스로 라우팅되는 방법을 지정 합니다. 이러한 정책은 Exchange UM 호스팅 보이스 메일에 대해 사용 하도록 설정 된 사용자 에게만 영향을 줍니다.  <br/><br/> 사용자가 호스팅된 보이스 메일을 사용할 수 있는지 여부를 확인 하려면 PowerShell 프롬프트에서 다음과 같은 명령을 실행 합니다.  <br/> \`Get-CsOnlineUser-Id "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>관련 주제
[Windows PowerShell을 사용 하 여 비즈니스용 skype online 관리를 위한 컴퓨터 설정](set-up-your-computer-for-windows-powershell.md)

  
 
