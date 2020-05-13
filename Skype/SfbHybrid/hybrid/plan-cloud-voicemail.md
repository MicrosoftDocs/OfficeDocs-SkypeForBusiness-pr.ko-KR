---
title: 온-프레미스 사용자를 위한 클라우드 음성 메일 서비스 계획 | PBX 비즈니스용 Skype 서버 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 이 문서에서는 Microsoft Cloud 음성 메일 서비스를 구현 하기 위한 혜택, 계획 고려 사항 및 요구 사항에 대해 설명 합니다. 클라우드 음성 메일을 구성 하는 방법에 대 한 자세한 내용은 클라우드 음성 메일 구성을 참조 하세요.
ms.openlocfilehash: 30a4983c79f4a7cddd274c272b5a094c17653bbb
ms.sourcegitcommit: 7c08d88dcaa85e34e93131bb9a5a64597c6d8155
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210634"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>온-프레미스 사용자를 위한 클라우드 음성 메일 서비스 계획

## <a name="overview"></a>개요

이 문서에서는 온-프레미스 사용자를 위해 Microsoft 클라우드 음성 메일 서비스를 구현 하기 위한 혜택, 계획 고려 사항 및 요구 사항에 대해 설명 합니다. 클라우드 음성 메일을 구성 하는 방법에 대 한 자세한 내용은 [클라우드 음성 메일 서비스 구성을](configure-cloud-voicemail.md)참조 하세요.

클라우드 음성 메일은 exchange UM (통합 메시징)을 사용 하 여 exchange Server 2019 또는 Exchange Online에 사서함이 있는 비즈니스용 Skype 2019 음성 사용자에 게 음성 메시징 기능을 제공 합니다. 클라우드 음성 메일은 온-프레미스 및 온라인 사용자 모두에 게 다음과 같은 이점을 제공 합니다.

- 향상 된 음성 기록의 음성 메일 응답 및 입금 기능

- 비즈니스용 Skype 온라인 또는 Outlook 클라이언트를 사용 하 여 사용자의 Exchange 사서함에 있는 음성 메일에 액세스

- Office 365 웹 기반 포털을 사용 하 여 음성 메일 옵션을 관리 하는 기능

- 온-프레미스 또는 클라우드에서 Exchange 사서함 지원

- Exchange Online 통합 메시징의 기존 사용자 인사말 활용

기능 비교에 대 한 자세한 내용은 [비즈니스용 Skype 서버 및 Exchange server 마이그레이션을 계획](plan-um-migration.md)합니다 .를 참조 하세요.

비즈니스용 Skype 서버 2019에서는 사서함이 이전 버전의 Exchange Server (2013, 2016)에 있는 사용자에 대해 Exchange UM을 계속 사용 합니다.  Exchange Server 및 비즈니스용 Skype 서버 버전을 기반으로 사용 되는 음성 메일 솔루션을 이해 하는 것은 비즈니스용 Skype 서버 2019 또는 Exchange Server 2019로의 마이그레이션을 계획 하는 데 있어 중요 한 요소입니다. 마이그레이션 및 상호 운용성에 대 한 자세한 내용은 [Plan For 비즈니스용 Skype 서버 및 Exchange Server migration](plan-um-migration.md)을 참조 하십시오.

클라우드 음성 메일을 사용 하는 경우에는 다음과 같은 이유로 관리 작업이 크게 간단해 집니다.

- Exchange UM 역할을 구성할 필요가 없습니다.
- 클라우드 음성 메일의 설치 작업은 더 간단 합니다.
- 음성 메일 기능에 대 한 업데이트는 클라우드에서 직접 배달 되므로 사용자는 CUs (누적 업데이트)에 대 한 종속성이 낮아 최신 기능 및 업데이트에 항상 액세스할 수 있습니다.
- 온-프레미스 및 온라인 Exchange 사서함 둘 다에 대해 동일한 컨트롤 집합을 사용 합니다. 이러한 컨트롤에 대 한 자세한 내용은 [전화 시스템 음성 메일 설정을](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)참조 하십시오.

다음 다이어그램에서는 하이브리드 배포의 클라우드 음성 메일을 보여 줍니다.

![SfB Cloud 음성 메일](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

응답 하지 않은 호출은 다음과 같이 처리 됩니다.  

1. 비즈니스용 Skype 2019 온-프레미스에 있는 사용자의 경우 온-프레미스 비즈니스용 Skype 서버에서 온라인 클라우드 음성 메일 서비스로 응답 하지 않은 전화가 전송 됩니다.
2. 이 서비스는 기록을 포함 하 여 음성 메일을 처리 합니다.
3. 그런 다음이 서비스는 사서함이 온-프레미스 또는 온라인 인지에 관계 없이 사용자의 Exchange 사서함에 있는 음성 메일을 저축금과 합니다.  
4. 사용자는 비즈니스용 Skype 또는 Outlook 클라이언트에서 음성 메일에 액세스할 수 있습니다.

## <a name="requirements"></a>요구 사항

다음 요구 사항에 따라 지원 되는 토폴로지에서 비즈니스용 Skype 서버를 이미 배포 했다고 가정 합니다.  요구 사항은 시나리오에 따라 달라 집니다.

- 이미 Exchange UM online을 사용 하 고 있고 비즈니스용 Skype 2019로 업그레이드 하는 경우 호스트 된 음성 메일 정책을 수정 하 고 호스팅 공급자가 올바르게 설정 되어 있는지 확인 해야 합니다. 자세한 내용은 [클라우드 음성 메일 서비스 구성을](configure-cloud-voicemail.md)참조 하세요.

- Exchange UM을 온-프레미스에서 사용 중이거나 Exchange UM online 및 온-프레미스를 사용 하는 사용자가 섞여 있는 경우에는 호스팅된 음성 메일 정책 및 호스팅 공급자를 모두 수정 해야 합니다.  자세한 내용은 [클라우드 음성 메일 서비스 구성을](configure-cloud-voicemail.md)참조 하세요.

- 클라우드 음성 메일의 새 구성을 위해 [클라우드 음성 메일 서비스 구성](configure-cloud-voicemail.md)에 설명 된 단계를 수행 합니다.

위의 요구 사항 외에도 다음 요구 사항을 Microsoft 클라우드 음성 메일 서비스에 연결 하도록 구성 해야 합니다.

- 하이브리드 연결 비즈니스용 Skype 서버가 이미 배포 되어 있고 온-프레미스 사용자가 클라우드 음성 메일을 사용 하도록 설정 하려는 경우 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다. 이를 분할 도메인 구성 이라고 합니다.

   자세한 내용은 비즈니스용 [Skype 서버 및 office 365의 하이브리드 연결 계획](plan-hybrid-connectivity.md) 및 [비즈니스용 Skype 서버 및 office 365 간의 하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요.

- 비즈니스용 Skype 서버에서 Enterprise Voice 및 호스팅된 음성 메일을 사용 하도록 설정 해야 합니다.

- 외부 EWS (Exchange 웹 서비스) URL 및 자동 검색을 설정 해야 하거나 일부 클라우드 음성 메일 기능이 제한 됩니다.

- 온-프레미스 전용 배포&#x2014;, 즉 Exchange 및 비즈니스용 Skype 온-프레미스 서버를&#x2014;하지만 클라우드 음성 메일을 활용 하려는 경우에는 전화 시스템 라이선스가 필요 합니다.

## <a name="migration-and-interoperability"></a>마이그레이션 및 상호 운용성

비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019을 배포 하려는 경우에는 음성 메시징에 대 한 지속적인 서비스를 위해 마이그레이션을 신중 하 게 계획 해야 합니다. 다음 사항에 유의해야 합니다.

- Exchange 서버 2019에서 더 이상 Exchange UM 기능을 제공 하지 않음
- 비즈니스용 Skype 서버 2019이 더 이상 Exchange Online UM에 통합 되지 않음

버전 상호 운용성 및 클라우드 음성 메일에 대해 지원 되는 토폴로지는 다음 표에 나와 있으며,이는 사용자가 사용할 수 있는 비즈니스용 Skype 서버 버전과 Exchange 사서함을 제공 하는 가능한 버전을 비교 합니다. Exchange Online 또는 Exchange Server 2019에서 비즈니스용 Skype 2019을 사용 하려는 경우에는 클라우드 음성 메일을 사용 해야 합니다.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| 비즈니스용 Skype 서버 2019 | Exchange Server UM | Exchange Server UM | 클라우드 음성 메일 | 클라우드 음성 메일 |
| 비즈니스용 Skype 서버 2015 | Exchange Server UM | Exchange Server UM | 클라우드 음성 메일 | 클라우드 음성 메일 |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | 미지원 | 클라우드 음성 메일 |

Microsoft는 다음과 같은 마이그레이션 경로를 권장 합니다.

- 비즈니스용 Skype 서버 2019로 업그레이드 하는 경우 exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 Exchange Server 2019을 사용 하는 경우 클라우드 음성 메일로 업그레이드 해야 합니다.
- Exchange Server 2019로 업그레이드 하는 경우 비즈니스용 Skype 서버 음성 메시징의 이전 버전의 Exchange Server UM을 사용 하는 경우에는 사서함 업그레이드 전에 비즈니스용 Skype 서버 2019로 업그레이드 하는 것이 좋습니다.  그렇지 않으면 음성 메시징 기능을 잃게 됩니다.
- 비즈니스용 skype 서버 2019로 업그레이드 하 고 Exchange Online UM과의 음성 메일에 비즈니스용 Skype 서버 2015을 구성 하는 경우 사용자의 음성 메일이 Exchange Online UM에서 클라우드 음성 2019 메일로 자동으로 마이그레이션됩니다. 

마이그레이션 계획에 대 한 자세한 내용은 [비즈니스용 Skype 서버 및 Exchange server 마이그레이션을 계획](plan-um-migration.md)합니다 .를 참조 하세요.
