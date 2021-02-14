---
title: Exchange 및 Sharepoint와의 통합
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
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
description: '요약: Exchange 및 SharePoint와의 비즈니스용 Skype 서버 2015 통합에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821108"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Exchange 및 Sharepoint와의 통합

**요약:** Exchange 및 SharePoint와의 비즈니스용 Skype 서버 2015 통합에 대해 자세히 알아보습니다.

Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 및 SharePoint Server와의 통합을 위해 비즈니스용 Skype 서버 2015 배포를 구성할 수 있습니다. 다음 표에 나열된 기능은 다른 설명이 없는 한 모든 클라이언트에서 지원됩니다. 클라이언트 지원에 대한 자세한 내용은 비즈니스용 Skype Online 클라이언트의 비즈니스용 [Skype](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) 및 비즈니스용 Skype Online 클라이언트 비교 표에 대한 데스크톱 클라이언트 기능 비교를 [참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=281902)

## <a name="integration-with-exchange-server"></a>통합 Exchange Server

다음 표에서는 하이브리드 배포와 통합된 경우 하이브리드 배포에서 지원되는 기능을 Microsoft Exchange Server.

 **비즈니스용 Skype 서버(프레미스 및 Exchange On-Premises)**


|**기능**|**참고**|
|:-----|:-----|
|Outlook의 IM/현재 상태  <br/> |자세한 내용은 IM 및 현재 상태 [를 참조하십시오.](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)  <br/> |
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> |자세한 내용은 비즈니스용 Skype 서버 [2015와](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)비즈니스용 Skype Exchange Server.  <br/> |
|IM/Presence in Outlook Web App  <br/> |자세한 내용은 비즈니스용 Skype 서버 [2015에서 하이브리드 환경 구성을 참조하세요.](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|모임을 통해 온라인 모임 예약 및 Outlook Web App  <br/> ||
|모바일 클라이언트의 IM/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임 참가  <br/> |자세한 내용은 모바일 배포를 [참조하십시오.](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)  <br/> |
|Outlook 일정 약속이 있는/약속 있는 일정 정보를 기준으로 상태 게시  <br/> ||
|연락처 목록(통합 연락처 저장소를 통해)  <br/> |Exchange 2016 또는 Exchange 2013이 필요합니다.  <br/> Lync 2013 또는 비즈니스용 Skype 데스크톱 클라이언트가 필요합니다.  <br/>  자세한 내용은 통합 연락처 저장소를 사용하도록 [비즈니스용 Skype 서버 2015 구성을 참조하세요.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)  <br/> |
|Lync 2013 클라이언트, 비즈니스용 Skype 클라이언트 및 Lync Web App의 고해상도 연락처 사진  <br/> |Exchange 2016 또는 Exchange 2013이 필요합니다.  <br/> 자세한 내용은 비즈니스용 Skype 서버 [2015에서](../deploy/integrate-with-exchange-server/high-resolution-photos.md)고해상도 사진 사용 구성을 참조하세요.  <br/> MAC 및 모바일용 비즈니스용 Skype 앱의 사진의 경우 비즈니스용 Skype 서버 2015와 Exchange Server 비즈니스용 Skype 서버 및 비즈니스용 [Skype](../deploy/integrate-with-exchange-server/configure-partner-applications.md)응용 프로그램 구성에 설명된 Exchange Server. <br/> |
|모임 위임  <br/> |두 사용자가 같은 포리스트에 온라인에 있는 경우 또는 두 사용자가 모두 온라인에 있는 경우 지원됩니다. 자세한 내용은 비즈니스용 Skype 하이브리드 [솔루션을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록됩니다.  <br/> ||
|Exchange에 콘텐츠(IM 및 모임) 보관  <br/> |Exchange 2016 또는 Exchange 2013이 필요합니다.  <br/> 자세한 내용은 보관에 대한 배포 [검사 목록을 참조하십시오.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|보관된 콘텐츠 검색  <br/> |Exchange 2016 또는 Exchange 2013이 필요합니다.  <br/> |
|음성 사서함  <br/> |자세한 내용은 온-프레미스 Exchange UM 배포를 참조하여 [Lync Server 2013 음성 메일을 제공합니다.](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)  <br/> |

 **비즈니스용 Skype 서버(프레미스 및 Exchange Online)**


|**기능**|**참고**|
|:-----|:-----|
|Outlook의 IM/현재 상태  <br/> |자세한 내용은 비즈니스용 Skype 서버 [2015와](../deploy/integrate-with-exchange-server/outlook-web-app.md) 비즈니스용 Skype 서버 간의 통합 구성을 Outlook Web App <br/> |
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> ||
|IM/Presence in Outlook Web App  <br/> |자세한 내용은 비즈니스용 Skype 서버 [2015와](../deploy/integrate-with-exchange-server/outlook-web-app.md) 비즈니스용 Skype 서버 간의 통합 구성을 Outlook Web App <br/> |
|2016년 8월 1일부로 온라인 모임 예약 및 Outlook Web App  <br/> |자세한 내용은 비즈니스용 Skype 서버 [2015와](../deploy/integrate-with-exchange-server/outlook-web-app.md) 비즈니스용 Skype 서버 간의 통합 구성을 Outlook Web App <br/> |
|모바일 클라이언트의 IM/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임 참가  <br/> ||
|Outlook 일정 약속이 있는/약속 있는 일정 정보를 기준으로 상태 게시  <br/> ||
|연락처 목록(통합 연락처 저장소를 통해)  <br/> |Lync Server 2013만 해당합니다. Lync 2013 또는 비즈니스용 Skype 데스크톱 클라이언트가 필요합니다.  <br/> 자세한 내용은 통합 연락처 저장소를 사용하도록 [비즈니스용 Skype 서버 2015 구성을 참조하세요.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 클라이언트, 비즈니스용 Skype 클라이언트 및 Lync Web App의 고해상도 연락처 사진  <br/> |자세한 내용은 비즈니스용 Skype 서버 [2015에서](../deploy/integrate-with-exchange-server/high-resolution-photos.md)고해상도 사진 사용 구성을 참조하세요.  <br/> MAC 및 모바일용 비즈니스용 Skype 앱의 사진의 경우 비즈니스용 Skype 서버 2015와 Exchange Server 간의 통합은 비즈니스용 Skype 서버와 비즈니스용 [Skype](../deploy/integrate-with-exchange-server/outlook-web-app.md)서버 간의 통합 구성에 설명된 Outlook Web App. <br/> |
|모임 위임  <br/> |두 사용자가 같은 포리스트에 온라인에 있는 경우 또는 두 사용자가 모두 온라인에 있는 경우 지원됩니다. 자세한 내용은 비즈니스용 Skype 하이브리드 [솔루션을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록됩니다.  <br/> ||
|Exchange에 콘텐츠(IM 및 모임) 보관  <br/> |자세한 내용은 보관에 대한 배포 [검사 목록을 참조하십시오.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|보관된 콘텐츠 검색  <br/> |자세한 내용은 [SharePoint eDiscovery 센터에 대한 Exchange 구성을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|음성 사서함  <br/> |자세한 내용은 [호스팅된 Exchange UM에서 Lync Server 2013 사용자 음성 메일 제공을 참조하십시오.](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)  <br/> |

 **비즈니스용 Skype Online 및 Exchange온-프레미스**


|**기능**|**참고**|
|:-----|:-----|
|Outlook의 현재 상태  <br/> ||
|Outlook 전자 메일에서 IM, PSTN 통화, Skype 통화 또는 화상 통화를 통해 응답  <br/> ||
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> ||
|모바일 클라이언트의 IM/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임 참가  <br/> ||
|Outlook 일정 약속이 있는/약속 있는 일정 정보를 기준으로 상태 게시  <br/> ||
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록됩니다.  <br/> ||
|Lync 2013 또는 비즈니스용 Skype 클라이언트의 고해상도 연락처 사진  <br/> |Exchange 2016 또는 Exchange 2013이 필요합니다. 사용자가 비즈니스용 Skype Online에 있는 경우 Lync Web App에서는 지원되지 않습니다.  <br/> |
|모임 위임  <br/> |두 사용자가 같은 포리스트에 온라인에 있는 경우 또는 두 사용자가 모두 온라인에 있는 경우 지원됩니다. 자세한 내용은 비즈니스용 Skype 하이브리드 [솔루션을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록됩니다.  <br/> ||
|서버 쪽 대화 기록  <br/> ||

 **비즈니스용 Skype Online 및 Exchange Online**


|**기능**|**참고**|
|:-----|:-----|
|Outlook의 IM/현재 상태  <br/> ||
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> ||
|IM/Presence in Outlook Web App  <br/> ||
|2016년 8월 1일부로 온라인 모임 예약 및 Outlook Web App  <br/> ||
|모바일 클라이언트의 IM/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임 참가  <br/> ||
|Outlook 일정 약속이 있는/약속 있는 일정 정보를 기준으로 상태 게시  <br/> ||
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록됩니다.  <br/> ||
|연락처 목록(통합 연락처 저장소를 통해)  <br/> |Lync Server 2013 또는 비즈니스용 Skype 클라이언트 필요  <br/> |
|Lync 2013, 비즈니스용 Skype 클라이언트 및 Lync Web App의 고해상도 연락처 사진  <br/> ||
|모임 위임  <br/> |두 사용자가 같은 포리스트에 온라인에 있는 경우 또는 두 사용자가 모두 온라인에 있는 경우 지원됩니다. 자세한 내용은 비즈니스용 Skype 하이브리드 [솔루션을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Exchange에 콘텐츠(IM 및 모임) 보관  <br/> ||
|보관된 콘텐츠 검색  <br/> ||
|음성 메일  <br/> ||

## <a name="integration-with-sharepoint"></a>SharePoint와의 통합

다음 표에는 SharePoint와 통합된 경우 하이브리드 배포에서 지원되는 기능이 나열되어 있습니다.

||**SharePoint On-premises**|**SharePoint Online**|
|:-----|:-----|:-----|
|**비즈니스용 Skype 서버 2015 On-premises** <br/> | 기술 검색 <br/>  SharePoint의 현재 상태 <br/> | SharePoint의 현재 상태 <br/> |
|**비즈니스용 Skype Online** <br/> | SharePoint의 현재 상태 <br/> | SharePoint의 현재 상태 <br/> |


