---
title: Exchange 및 Sharepoint와의 통합
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: '요약: Exchange 및 SharePoint와의 비즈니스용 Skype 서버 2015 통합에 대해 알아보세요.'
ms.openlocfilehash: 18839125faee2dfd27ad3843e37b723f56581ff3
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231149"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Exchange 및 Sharepoint와의 통합

**요약:** Exchange 및 SharePoint와의 비즈니스용 Skype 서버 2015 통합에 대해 알아보세요.

Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange server 2010 및 SharePoint Server (온-프레미스 및 온라인)와 통합을 위해 비즈니스용 Skype 서버 2015 배포를 구성할 수 있습니다. 다음 표에 나열 된 기능은 달리 지정 하지 않는 한 모든 클라이언트에서 지원 됩니다. 클라이언트 지원에 대 한 자세한 내용은 비즈니스용 Skype online 및 비즈니스용 skype Online 클라이언트 비교 표에 대 한 [데스크톱 클라이언트 기능 비교](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) 를 참조 [하세요.](https://go.microsoft.com/fwlink/p/?LinkId=281902)

## <a name="integration-with-exchange-server"></a>Exchange Server와 통합

다음 표에는 Microsoft Exchange Server와 통합할 때 하이브리드 배포에서 지원 되는 기능이 나와 있습니다.

 **온-프레미스의 비즈니스용 Skype 서버 온-프레미스 및 Exchange**


|**기능**|**상속자**|
|:-----|:-----|
|Outlook에서 메신저 대화/현재 상태  <br/> |자세한 내용은 [메신저 대화 및 현재 상태](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)를 참조 하세요.  <br/> |
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> |자세한 내용은 [Exchange server와 비즈니스용 Skype 서버 2015 통합](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)을 참조 하세요.  <br/> |
|Outlook Web App에서 메신저 대화/현재 상태  <br/> |자세한 내용은 비즈니스용 [Skype 서버 2015에서 하이브리드 환경 구성을](../manage/authentication/configure-a-hybrid-environment.md)참조 하세요.  <br/> |
|Outlook Web App을 통해 온라인 모임 예약 및 참가  <br/> ||
|모바일 클라이언트에서 메신저 대화/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임 참가  <br/> |자세한 내용은 [이동성 배포](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)를 참조 하세요.  <br/> |
|Outlook 일정 약속 있음/없음 정보를 기준으로 게시 상태  <br/> ||
|연락처 목록 (통합 된 대화 상대 저장소를 통해)  <br/> |Exchange 2016 또는 Exchange 2013이 필요 합니다.  <br/> Lync 2013 또는 비즈니스용 Skype 데스크톱 클라이언트가 필요 합니다.  <br/>  자세한 내용은 [통합 된 대화 상대 저장소를 사용 하도록 비즈니스용 Skype 서버 2015 구성을](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)참조 하세요.  <br/> |
|Lync 2013 클라이언트, 비즈니스용 Skype 클라이언트, Lync Web App의 고해상도 연락처 사진  <br/> |Exchange 2016 또는 Exchange 2013이 필요 합니다.  <br/> 자세한 내용은 비즈니스용 [Skype 서버 2015에서 고해상도 사진 사용 구성을](../deploy/integrate-with-exchange-server/high-resolution-photos.md)참조 하세요.  <br/> MAC 용 비즈니스용 Skype 앱에 있는 사진의 경우 비즈니스용 skype server 2015 및 Exchange Server의 통합은 비즈니스용 [Skype 서버 및 Exchange server의 파트너 응용 프로그램 구성](../deploy/integrate-with-exchange-server/configure-partner-applications.md)에 설명 된 대로 설정 되어 있어야 합니다. <br/> |
|모임 위임  <br/> |두 사용자가 모두 같은 포리스트에 온라인 상태 이거나 둘 다 온 경우에만 지원 됩니다. 자세한 내용은 [비즈니스용 Skype 하이브리드 솔루션](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)을 참조 하세요. <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됩니다.  <br/> ||
|Exchange에서 콘텐츠 (IM 및 모임) 보관  <br/> |Exchange 2016 또는 Exchange 2013이 필요 합니다.  <br/> 자세한 내용은 [보관을 위한 배포 검사 목록을](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)참조 하세요.  <br/> |
|보관 된 콘텐츠 검색  <br/> |Exchange 2016 또는 Exchange 2013이 필요 합니다.  <br/> |
|음성 메일  <br/> |자세한 내용은 온 [-프레미스 EXCHANGE UM 배포를 참조 하 여 Lync Server 2013 음성 메일을 제공](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)하세요.  <br/> |

 **온-프레미스 및 Exchange Online의 비즈니스용 Skype 서버**


|**기능**|**상속자**|
|:-----|:-----|
|Outlook에서 메신저 대화/현재 상태  <br/> |자세한 내용은 온 [-프레미스 비즈니스용 Skype 서버 2015 및 Outlook Web App 간 통합 구성을](../deploy/integrate-with-exchange-server/outlook-web-app.md) 참조 하세요. <br/> |
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> ||
|Outlook Web App에서 메신저 대화/현재 상태  <br/> |자세한 내용은 온 [-프레미스 비즈니스용 Skype 서버 2015 및 Outlook Web App 간 통합 구성을](../deploy/integrate-with-exchange-server/outlook-web-app.md) 참조 하세요. <br/> |
|Outlook Web App에서 온라인 모임 예약 및 참가  <br/> |자세한 내용은 온 [-프레미스 비즈니스용 Skype 서버 2015 및 Outlook Web App 간 통합 구성을](../deploy/integrate-with-exchange-server/outlook-web-app.md) 참조 하세요. <br/> |
|모바일 클라이언트에서 메신저 대화/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임 참가  <br/> ||
|Outlook 일정 약속 있음/없음 정보를 기준으로 게시 상태  <br/> ||
|연락처 목록 (통합 된 대화 상대 저장소를 통해)  <br/> |Lync 서버 2013만 해당 됩니다. Lync 2013 또는 비즈니스용 Skype 데스크톱 클라이언트가 필요 합니다.  <br/> 자세한 내용은 [통합 된 대화 상대 저장소를 사용 하도록 비즈니스용 Skype 서버 2015 구성](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) 을 참조 하세요. <br/> |
|Lync 2013 클라이언트, 비즈니스용 Skype 클라이언트, Lync Web App의 고해상도 연락처 사진  <br/> |자세한 내용은 비즈니스용 [Skype 서버 2015에서 고해상도 사진 사용 구성을](../deploy/integrate-with-exchange-server/high-resolution-photos.md)참조 하세요.  <br/> MAC 용 비즈니스용 Skype 앱에 있는 사진에는 비즈니스용 skype Server 2015 및 Exchange Server 간 통합이 [온-프레미스 비즈니스용 Skype 서버와 Outlook Web app의 통합 구성](../deploy/integrate-with-exchange-server/outlook-web-app.md)에 설명 된 대로 설정 되어 있어야 합니다. <br/> |
|모임 위임  <br/> |두 사용자가 모두 같은 포리스트에 온라인 상태 이거나 둘 다 온 경우에만 지원 됩니다. 자세한 내용은 [비즈니스용 Skype 하이브리드 솔루션](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)을 참조 하세요. <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록 됩니다.  <br/> ||
|Exchange에서 콘텐츠 (IM 및 모임) 보관  <br/> |자세한 내용은 [보관을 위한 배포 검사 목록을](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)참조 하세요.  <br/> |
|보관 된 콘텐츠 검색  <br/> |자세한 내용은 [SharePoint 용 Exchange EDiscovery 센터 구성](https://go.microsoft.com/fwlink/p/?LinkId=285448) 을 참조 하세요. <br/> |
|음성 메일  <br/> |자세한 내용은 [호스팅된 EXCHANGE UM에서 Lync Server 2013 사용자에 게 음성 메일 제공](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)을 참조 하세요.  <br/> |

 **비즈니스용 Skype Online 및 온-프레미스 교환**


|**기능**|**상속자**|
|:-----|:-----|
|Outlook에서의 현재 상태  <br/> ||
|Outlook 전자 메일에서 IM, PSTN 통화, Skype 통화 또는 영상 통화를 통해 응답  <br/> ||
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> ||
|모바일 클라이언트에서 메신저 대화/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임 참가  <br/> ||
|Outlook 일정 약속 있음/없음 정보를 기준으로 게시 상태  <br/> ||
|부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됩니다.  <br/> ||
|Lync 2013 또는 비즈니스용 Skype 클라이언트의 고해상도 연락처 사진  <br/> |Exchange 2016 또는 Exchange 2013이 필요 합니다. 이 기능은 사용자가 비즈니스용 Skype Online으로 이동할 때 Lync Web App에서 지원 되지 않습니다.  <br/> |
|모임 위임  <br/> |두 사용자가 모두 같은 포리스트에 온라인 상태 이거나 둘 다 온 경우에만 지원 됩니다. 자세한 내용은 [비즈니스용 Skype 하이브리드 솔루션](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)을 참조 하세요. <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록 됩니다.  <br/> ||
|서버 쪽 대화 내용  <br/> ||

 **비즈니스용 Skype Online 및 Exchange Online**


|**기능**|**상속자**|
|:-----|:-----|
|Outlook에서 메신저 대화/현재 상태  <br/> ||
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> ||
|Outlook Web App에서 메신저 대화/현재 상태  <br/> ||
|Outlook Web App에서 온라인 모임 예약 및 참가  <br/> ||
|모바일 클라이언트에서 메신저 대화/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임 참가  <br/> ||
|Outlook 일정 약속 있음/없음 정보를 기준으로 게시 상태  <br/> ||
|부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됩니다.  <br/> ||
|연락처 목록 (통합 된 대화 상대 저장소를 통해)  <br/> |Lync Server 2013 또는 비즈니스용 Skype 클라이언트 필요  <br/> |
|Lync 2013, 비즈니스용 Skype 클라이언트, Lync Web App의 고해상도 연락처 사진  <br/> ||
|모임 위임  <br/> |두 사용자가 모두 같은 포리스트에 온라인 상태 이거나 둘 다 온 경우에만 지원 됩니다. 자세한 내용은 [비즈니스용 Skype 하이브리드 솔루션](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)을 참조 하세요. <br/> |
|Exchange에서 콘텐츠 (IM 및 모임) 보관  <br/> ||
|보관 된 콘텐츠 검색  <br/> ||
|음성 메일  <br/> ||

## <a name="integration-with-sharepoint"></a>SharePoint와 통합

다음 표에는 SharePoint와 통합할 때 하이브리드 배포에서 지원 되는 기능이 나와 있습니다.

||**SharePoint 온-프레미스**|**SharePoint Online**|
|:-----|:-----|:-----|
|**비즈니스용 Skype 서버 2015 온-프레미스** <br/> | 기술 검색 <br/>  SharePoint에서 현재 상태 <br/> | SharePoint에서 현재 상태 <br/> |
|**비즈니스용 Skype Online** <br/> | SharePoint에서 현재 상태 <br/> | SharePoint에서 현재 상태 <br/> |


