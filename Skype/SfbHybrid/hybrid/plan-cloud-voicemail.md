---
title: 온-프레미스 사용자 용 클라우드 보이스 메일 서비스 계획 | PBX 비즈니스용 Skype 서버 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 이 문서에서는 Microsoft 클라우드 보이스 메일 서비스를 구현 하기 위한 이점, 계획 고려 사항 및 요구 사항을 설명 합니다. 클라우드 보이스 메일을 구성 하는 방법에 대 한 자세한 내용은 클라우드 보이스 메일 구성을 참조 하세요.
ms.openlocfilehash: 0071154ab1b9c1211725dd9b6addc2dfd5449e15
ms.sourcegitcommit: 46fb558814cb6bd7d70729eac590afd51fc6606e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2019
ms.locfileid: "36185532"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>온-프레미스 사용자를 위한 클라우드 보이스 메일 서비스 계획

## <a name="overview"></a>개요

이 문서에서는 온-프레미스 사용자를 위해 Microsoft 클라우드 보이스 메일 서비스를 구현 하기 위한 이점, 계획 고려 사항, 요구 사항에 대해 설명 합니다. 클라우드 보이스 메일을 구성 하는 방법에 대 한 자세한 내용은 [클라우드 보이스 메일 서비스 구성을](configure-cloud-voicemail.md)참조 하세요.

클라우드 보이스 메일은 exchange UM (통합 메시징)의 위치를 사용 하 여 비즈니스용 Skype 2019 또는 Exchange Online 2019에서 사서함을 보유 하 고 있는 비즈니스에 대 한 음성 메시지 기능을 제공 합니다. 클라우드 보이스 메일은 온-프레미스와 온라인 사용자 모두에 게 다음과 같은 이점을 제공 합니다.

- 향상 된 음성 인식 기능으로 음성 메일 응답 및 입금

- 비즈니스용 Skype Online 또는 Outlook 클라이언트를 사용 하 여 사용자의 Exchange 사서함에 있는 보이스 메일에 액세스

- Office 365 웹 기반 포털을 사용 하 여 음성 메일 옵션을 관리 하는 기능

- 온-프레미스 또는 클라우드에서 Exchange 사서함 지원

- Exchange Online 통합 메시징에서 기존 사용자 인사말 활용

기능 비교에 대 한 자세한 내용은 비즈니스용 [Skype 서버 및 Exchange server 마이그레이션 계획](plan-um-migration.md)을 참조 하세요.

비즈니스용 Skype 서버 2019는 사서함이 이전 버전의 Exchange Server (2013, 2016)에 있는 사용자에 게 Exchange UM을 계속 사용 합니다.  Exchange Server 및 비즈니스용 Skype Server 버전을 기반으로 사용 되는 보이스 메일 솔루션에 대 한 이해는 비즈니스용 Skype 서버 2019 또는 Exchange Server 2019에 대 한 마이그레이션을 계획 하는 데 중요 한 역할을 합니다. 마이그레이션 및 상호 운용성에 대 한 자세한 내용은 비즈니스용 [Skype 서버 및 Exchange server 마이그레이션 계획](plan-um-migration.md)을 참조 하세요.

클라우드 보이스 메일을 사용 하면 다음과 같은 이유로 관리 작업이 매우 간단해 집니다.

- Exchange UM 역할을 구성할 필요는 없습니다.
- 클라우드 보이스 메일에 대 한 설정 작업은 간단 합니다.
- 보이스 메일 기능에 대 한 업데이트는 클라우드에서 직접 제공 되므로 사용자는 항상 CUs (누적 업데이트에 대 한 종속성이 낮은)에 대 한 최신 기능 및 업데이트에 액세스할 수 있습니다.
- 온-프레미스 및 온라인 Exchange 사서함 모두에 대해 동일한 컨트롤 집합을 사용 합니다. 이러한 컨트롤에 대 한 자세한 내용은 [전화 시스템 보이스 메일 설정을](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)참조 하세요.

다음 다이어그램은 하이브리드 배포의 클라우드 보이스 메일을 보여줍니다.

![SfB 구름 보이스 메일](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

응답 하지 않은 호출은 다음과 같이 처리 됩니다.  

1. 비즈니스용 Skype 2019 온-프레미스에 있는 사용자의 경우, 응답 하지 않은 통화는 온-프레미스 비즈니스용 Skype 서버에서 온라인 클라우드 보이스 메일 서비스로 전송 됩니다.
2. 이 서비스는 기록을 포함 하 여 보이스 메일을 처리 합니다.
3. 그런 다음 서비스는 사서함이 온-프레미스 또는 온라인 인지 여부에 관계 없이 사용자의 Exchange 사서함에 있는 보이스 메일을 저축과.  
4. 사용자는 비즈니스용 Skype 또는 Outlook 클라이언트에서 보이스 메일에 액세스할 수 있습니다.

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원 되는 토폴로지에서 이미 비즈니스용 Skype 서버를 배포 하는 것으로 가정 합니다.  요구 사항은 시나리오에 따라 달라 집니다.

- Exchange UM online을 이미 사용 하 고 있고 비즈니스용 Skype 2019으로 업그레이드 한 경우에는 호스트 된 음성 메일 정책을 수정 하 고 호스팅 공급자가 올바르게 설정 되어 있는지 확인 해야 합니다. 자세한 내용은 [클라우드 보이스 메일 서비스 구성을](configure-cloud-voicemail.md)참조 하세요.

- 온-프레미스에 Exchange UM을 사용 중이거나 Exchange UM online 및 온-프레미스를 사용 하는 사용자가 섞여 있는 경우에는 호스팅된 음성 메일 정책 및 호스팅 공급자를 모두 수정 해야 합니다.  자세한 내용은 [클라우드 보이스 메일 서비스 구성을](configure-cloud-voicemail.md)참조 하세요.

- 클라우드 보이스 메일을 새로 구성 하려면 [클라우드 보이스 메일 서비스 구성](configure-cloud-voicemail.md)에 설명 된 단계를 따르세요.

위의 요구 사항 외에도 다음 요구 사항을 Microsoft 클라우드 보이스 메일 서비스에 연결 하도록 구성 해야 합니다.

- 하이브리드 연결. 비즈니스용 Skype 서버를 이미 배포 하 고 온-프레미스 사용자에 게 클라우드 보이스 메일을 사용 하려는 경우 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다. 이를 도메인 분할 구성이 라고도 합니다.

   자세한 내용은 비즈니스용 [Skype 서버 및 office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md) 을 참조 하 고 비즈니스용 [Skype 서버와 office 365의 하이브리드 연결을 구성](configure-hybrid-connectivity.md)합니다.

- 비즈니스용 Skype 서버에서 엔터프라이즈 음성과 호스팅 보이스 메일에 대해 온-프레미스 사용자를 사용 하도록 설정 해야 합니다.

- 외부 EWS (Exchange Web Services) URL 및 자동 검색을 설정 해야 하거나 일부 클라우드 음성 메일 기능이 제한 됩니다.

- 온-프레미스 전용 배포&#x2014;인 경우 Exchange 및 비즈니스용 Skype 온-프레미스 서버만&#x2014;있지만, 클라우드 보이스 메일을 활용 하려는 경우 라이선스는 추가로 필요 하지 않습니다.

## <a name="migration-and-interoperability"></a>마이그레이션 및 상호 운용성

비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019을 배포 하려는 경우에는 음성 메시지 서비스를 계속 해 서 사용할 수 있도록 마이그레이션을 계획 해야 합니다. 다음 사항에 유의 하세요.

- Exchange Server 2019에서 더 이상 Exchange UM 기능을 제공 하지 않음
- 비즈니스용 Skype 서버 2019이 더 이상 Exchange Online UM과 통합 되지 않음

클라우드 보이스 메일에 대 한 버전 상호 운용성 및 지원 되는 토폴로지는 다음 표에 나와 있으며,이는 사용자가 현재 속해 있을 수 있는 비즈니스용 Skype 서버 버전과 해당 Exchange 사서함을 제공 하는 가능한 버전을 비교 합니다. 클라우드 보이스 메일은 비즈니스용 Skype 서버 및 Exchange Server 2019 또는 Exchange Online 에서만 작동 합니다.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| 비즈니스용 Skype 서버 2019 | Exchange Server UM | Exchange Server UM | 구름 보이스 메일 | 구름 보이스 메일 |
| 비즈니스용 Skype 서버 2015 | Exchange Server UM | Exchange Server UM | 클라우드 보이스 메일<sup>1</sup> | 구름 보이스 메일 <br> Exchange Online UM<sup>2</sup> |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | 지원 되지 않음 | 구름 보이스 메일 <br> Exchange Online UM<sup>2</sup> |

<sup>1</sup> 아직이 옵션이 표시 되지 않는 경우 현재 롤아웃 중 이며 아직 조직에서 사용할 수 없을 수도 있습니다. 클라우드 보이스 메일에 대 한 계획 된 연결에 대 한 옵트인에는 [Exchange 통합 메시징 온라인 마이그레이션 지원](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support
) 에서 6 단계를 참조 하세요.

<sup>2</sup> 이 (가) 사용 되지 않습니다. 자세한 내용은 [Exchange 통합 메시징 온라인 마이그레이션 지원](../../sfbserver2019/plan/exchange-unified-messaging-online-migration-support.md) 을 참조 하세요. 

Microsoft는 다음 마이그레이션 경로를 권장 합니다.

- 비즈니스용 Skype 서버 2019으로 업그레이드 하는 경우 exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 Exchange Server 2019을 사용 하는 경우에는 클라우드 보이스 메일로 업그레이드 해야 합니다.
- Exchange Server 2019으로 업그레이드 하는 경우 비즈니스용 Skype Server voice messaging 용 Exchange Server UM의 이전 버전을 사용 하는 경우 사서함 업그레이드 전에 비즈니스용 Skype Server 2019으로 업그레이드 하는 것이 좋습니다.  그렇지 않으면 음성 메시지 기능이 손실 됩니다.
- 비즈니스용 Skype 서버 2019으로 업그레이드 하는 경우 Exchange Online UM을 사용 하 여 보이스 메일을 비즈니스용 Skype Server 2015를 보유 하 고 있는 경우, 사용자의 음성 메일은 계정이 이동할 때 Exchange Online UM에서 클라우드 음성 메일로 자동으로 마이그레이션됩니다. 비즈니스용 Skype 서버 2019. 

마이그레이션 계획에 대 한 자세한 내용은 비즈니스용 [Skype 서버 및 Exchange server 마이그레이션 계획](plan-um-migration.md)을 참조 하세요.
