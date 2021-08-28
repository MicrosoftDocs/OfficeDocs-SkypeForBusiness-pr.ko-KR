---
title: 허용된 구성원 선택
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 범주를 올바르게 사용하여 영구 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다. 영구 채팅 관리자는 각 범주에 대해 AllowedMembers 및 Creators를 정의할 수 있으며 범주에서 만든 모든 채팅방에 적용할 기본 채팅방 설정 및 동작을 정의할 수도 있습니다. 영구 채팅 관리자는 제어판 또는 cmdlet을 사용하여 범주를 Windows PowerShell 관리합니다.
ms.openlocfilehash: e6abad4444624101dd1971ce1525abaebdfc491a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601543"
---
# <a name="select-allowed-members"></a>허용된 구성원 선택

범주를 올바르게 사용하여 영구 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다. 영구 채팅 관리자는 각 범주에 **대해 AllowedMembers** 및 **Creators를** 정의할 수 있으며 범주에서 만든 모든 채팅방에 적용할 기본 채팅방 설정 및 동작을 정의할 수도 있습니다. 영구 채팅 관리자는 제어판 또는 cmdlet을 사용하여 범주를 Windows PowerShell 관리합니다.

범주의 작성자로 식별되는 사용자, OU(조직 구성 단위) 및 사용자 그룹은 해당 범주에서 대화방을 만들 수 있는 개인과 그룹입니다. 범주를 만든 후 범주의 **AllowedMembers** 목록에서 사용자, US 및 사용자 그룹을 채팅방 관리자 및 구성원으로 선택하여 채팅방을 관리하고 채팅방에 참가할 수 있습니다.

## <a name="tasks-that-you-can-perform"></a>수행할 수 있는 작업

허용된 구성원 선택 페이지에서는 **다음 작업을 수행할 수** 있습니다.

- [범주 구성](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [새 영구 채팅 서버 기능](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

비즈니스용 Skype 서버 제어판을 사용하여 수행할 수 있는 다양한 절차에 대한 자세한 내용은 [Manage 비즈니스용 Skype 서버 2015를 참조합니다.](../../manage/manage.md)

## <a name="to-configure-categories-for-chat-rooms"></a>채팅방에 대해 범주를 구성하려면

구성원 **자격의**  허용 구성원 섹션에서 범주에 속하는 채팅방의 구성원으로 추가될 수 있는 사용자 및 기타 Active Directory 도메인 서비스 계정(사용자, 메일 그룹, 조직 구성 단위 등)을 추가하거나 제거합니다. 특정 범주에서 허용된 계정은 방의 구성원만 디렉터리에서 방을 검색할 수 있도록 방이 숨겨져 있지 않은 한 해당 범주에서 방을 검색할 수 있습니다.


영구 채팅 서버 기능에 대한 자세한 내용은 계획 설명서에서 [Overview of Persistent Chat Server를](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) 참조하십시오. 영구 채팅 서버 구성을 사용하는 데 대한 자세한 내용은 배포 설명서의 [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) 및 작업 설명서의 [Managing Lync Server 2013, Persistent Chat Server를](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) 참조하십시오.

## <a name="see-also"></a>참고 항목

[영구 채팅 구성원 이해](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)