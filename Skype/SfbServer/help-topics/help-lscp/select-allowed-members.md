---
title: 허용 구성원 선택
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 일관 된 채팅방을 만들고 관리 하는 것은 범주를 올바르게 사용 하는 것 보다 훨씬 더 쉽습니다. 영구 채팅 관리자는 각 범주에 대해 AllowedMembers 및 작성자를 정의할 수 있으며, 범주에서 만든 모든 채팅방에 적용 되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다. 영구 채팅 관리자는 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 합니다.
ms.openlocfilehash: 916077fe25e1616888dd58dc40f0ef0f14c61e7a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699703"
---
# <a name="select-allowed-members"></a>허용 구성원 선택

일관 된 채팅방을 만들고 관리 하는 것은 범주를 올바르게 사용 하는 것 보다 훨씬 더 쉽습니다. 영구 채팅 관리자는 각 범주에 대해 **Allowedmembers** 및 **작성자** 를 정의할 수 있으며, 범주에서 만든 모든 채팅방에 적용 되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다. 영구 채팅 관리자는 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 합니다.

범주의 작성자로 식별되는 사용자, OU(조직 구성 단위), 사용자 그룹은 해당 범주에서 채팅방을 만들 수 있는 개인과 그룹입니다. 범주가 만들어진 후에는 범주의 **Allowedmembers** 목록에서 사용자, ou 및 사용자 그룹을 선택 하 여 채팅방에 관리 하 고 참여할 수 있습니다.

## <a name="tasks-that-you-can-perform"></a>수행할 수 있는 작업

**허용 구성원 선택** 페이지에서는 다음 작업을 수행할 수 있습니다.

- [Configure Categories](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [New Persistent Chat Server Features](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

비즈니스용 Skype 서버 제어판을 사용 하 여 수행할 수 있는 다양 한 절차에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015 관리](../../manage/manage.md)를 참조 하세요.

## <a name="to-configure-categories-for-chat-rooms"></a>채팅방에 대한 범주를 구성하려면

**구성원 자격**의 허용 된 **구성원** 섹션에서 사용자 및 기타 Active Directory 도메인 서비스 주체 (사용자, 메일 그룹, 조직 구성 단위 등)를 추가 하거나 제거 하 여 범주에 속하는 채팅방의 구성원으로 추가할 수 있도록 허용 합니다. 특정 범주에서 허용된 계정은 채팅방의 구성원만 디렉터리에서 채팅방을 검색할 수 있도록 채팅방이 숨겨져 있지 않은 한 해당 범주에서 채팅방을 검색할 수 있습니다.


영구 채팅 서버 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [영구 채팅 서버 개요](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 를 참조 하세요. 영구 채팅 서버 구성을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서의 [영구 채팅 서버 구성](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) 및 운영 설명서의 [Lync Server 2013, 영구 채팅 서버 관리](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) 를 참조 하세요.

## <a name="see-also"></a>참고 항목

[Understanding Persistent Chat Membership](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
