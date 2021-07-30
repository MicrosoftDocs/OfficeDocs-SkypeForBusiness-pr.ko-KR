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
description: '요약: 2015 및 비즈니스용 Skype 서버 통합에 대해 Exchange SharePoint.'
ms.openlocfilehash: 7e5303f5e47a2cfb017c893acbb63cce7e1521e7
ms.sourcegitcommit: d0fb9035903d9e1ce184417250913db10608b1a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2021
ms.locfileid: "53660766"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Exchange 및 Sharepoint와의 통합

**요약:** 2015 및 비즈니스용 Skype 서버 통합에 대해 Exchange SharePoint.

Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 및 SharePoint Server와의 통합을 위해 비즈니스용 Skype 서버 2015 배포를 구성할 수 있습니다. 다른 설명이 없는 한 다음 표에 나열된 기능은 모든 클라이언트에서 지원됩니다. 클라이언트 지원에 대한 자세한 [](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) 내용은 비즈니스용 Skype 및 비즈니스용 Skype Online용 클라이언트 비교 표에 대한 데스크톱 클라이언트 기능 비교를 비즈니스용 Skype 온라인 클라이언트 비교를 [참조하세요.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>통합 Exchange Server

다음 표에서는 하이브리드 배포와 통합된 경우 하이브리드 배포에서 지원되는 기능을 Microsoft Exchange Server.

 **비즈니스용 Skype 서버 및 Exchange 및**


|**기능**|**참고**|
|:-----|:-----|
|im/Presence in Outlook  <br/> |자세한 내용은 [IM 및 현재 상태 를 참조하세요.](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)  <br/> |
|모임을 통해 온라인 모임 예약 및 Outlook  <br/> |자세한 내용은 [2015와](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)비즈니스용 Skype 서버 통합을 Exchange Server.  <br/> |
|im/Presence in Outlook Web App  <br/> |자세한 내용은 [Configure a hybrid environment in 비즈니스용 Skype 서버 2015을 참조하십시오.](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|모임을 통해 온라인 모임 예약 및 참가 Outlook Web App  <br/> ||
|모바일 클라이언트의 IM/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임에 참가  <br/> |자세한 내용은 [Deploying Mobility을 참조하십시오.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)  <br/> |
|약속이 있는 약속 Outlook 정보를 기반으로 상태 게시  <br/> ||
|연락처 목록(통합 연락처 저장소를 통해)  <br/> |2016 Exchange 2013 또는 Exchange 필요합니다.  <br/> Lync 2013 또는 비즈니스용 Skype 클라이언트가 필요합니다.  <br/>  자세한 내용은 [Configure 비즈니스용 Skype 서버 2015 to use the unified contact store을 참조하십시오.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)  <br/> |
|Lync 2013 클라이언트, 비즈니스용 Skype 및 Lync Web App의 고해상도 연락처 사진  <br/> |2016 Exchange 2013 또는 Exchange 필요합니다.  <br/> 자세한 내용은 [Configure the use of high-resolution photos in 비즈니스용 Skype 서버 2015을 참조하십시오.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> MAC 및 모바일용 비즈니스용 Skype 사진의 경우 비즈니스용 Skype 서버 2015와 Exchange Server 간의 통합은 [configure partner applications in 비즈니스용 Skype 서버 and Exchange Server.](../deploy/integrate-with-exchange-server/configure-partner-applications.md) <br/> |
|모임 위임  <br/> |두 사용자가 동일한 포리스트에 온라인에 있는 경우 또는 두 사용자가 모두 온라인에 있는 경우만 지원됩니다. 자세한 내용은 하이브리드 솔루션 [비즈니스용 Skype 참조하세요.](/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록됩니다.  <br/> ||
|IM 및 모임의 콘텐츠 보관 Exchange  <br/> |2016 Exchange 2013 또는 Exchange 필요합니다.  <br/> 자세한 내용은 [Deployment Checklist for Archiving을 참조하십시오.](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|보관된 콘텐츠 검색  <br/> |2016 Exchange 2013 또는 Exchange 필요합니다.  <br/> |
|음성 사서함  <br/> |자세한 내용은 [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail을 참조하십시오.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)  <br/> |

 **비즈니스용 Skype 서버 및 Exchange Online**


|**기능**|**참고**|
|:-----|:-----|
|im/Presence in Outlook  <br/> |자세한 내용은 [Configure integration between on-premises 비즈니스용 Skype 서버 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|모임을 통해 온라인 모임 예약 및 Outlook  <br/> ||
|im/Presence in Outlook Web App  <br/> |자세한 내용은 [Configure integration between on-premises 비즈니스용 Skype 서버 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|2016년 8월부터 온라인 모임 예약 및 Outlook Web App  <br/> |자세한 내용은 [Configure integration between on-premises 비즈니스용 Skype 서버 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|모바일 클라이언트의 IM/현재 상태  <br/> ||
|모바일 클라이언트에서 온라인 모임에 참가  <br/> ||
|약속이 있는 약속 Outlook 정보를 기반으로 상태 게시  <br/> ||
|연락처 목록(통합 연락처 저장소를 통해)  <br/> |Lync Server 2013만 해당합니다. Lync 2013 또는 비즈니스용 Skype 클라이언트가 필요합니다.  <br/> 자세한 내용은 [Configure 비즈니스용 Skype 서버 2015 to use the unified contact store을 참조하십시오.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 클라이언트, 비즈니스용 Skype 및 Lync Web App의 고해상도 연락처 사진  <br/> |자세한 내용은 [Configure the use of high-resolution photos in 비즈니스용 Skype 서버 2015을 참조하십시오.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> MAC 및 모바일용 비즈니스용 Skype 사진의 경우 비즈니스용 Skype 서버 2015와 Exchange Server 간의 통합은 Configure integration between [on-premises 비즈니스용 Skype 서버 and Outlook Web App.](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|모임 위임  <br/> |두 사용자가 동일한 포리스트에 온라인에 있는 경우 또는 두 사용자가 모두 온라인에 있는 경우만 지원됩니다. 자세한 내용은 하이브리드 솔루션 [비즈니스용 Skype 참조하세요.](/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 사서함에 Exchange 기록됩니다.  <br/> ||
|IM 및 모임의 콘텐츠 보관 Exchange  <br/> |자세한 내용은 [Deployment Checklist for Archiving을 참조하십시오.](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|보관된 콘텐츠 검색  <br/> |자세한 내용은 Configure [Exchange for SharePoint eDiscovery Center을 참조하십시오.](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|음성 사서함  <br/> |자세한 내용은 [Hosted Exchange UM에서 Lync Server 2013 Users Voice Mail 제공을 참조하십시오.](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)  <br/> |


## <a name="integration-with-sharepoint"></a>통합 SharePoint

다음 표에서는 하이브리드 배포와 통합된 경우 하이브리드 배포에서 지원되는 기능을 SharePoint.

||**SharePoint 프레미스**|**SharePoint Online**|
|:-----|:-----|:-----|
|**비즈니스용 Skype 서버 2015 On-premises** <br/> | 기술 검색 <br/>  현재 SharePoint <br/> | 현재 SharePoint <br/> |
|**비즈니스용 Skype Online** <br/> | 현재 SharePoint <br/> | 현재 SharePoint <br/> |
