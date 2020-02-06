---
title: 비즈니스용 Skype 서버용에 대 한 RBAC (역할 기반 액세스 제어)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 비즈니스용 Skype 서버에는 관리 작업을 위임할 수 있는 RBAC (역할 기반 액세스 제어) 그룹이 포함 되어 있으며 보안에 대 한 높은 표준도 유지 됩니다. 이러한 그룹은 포리스트 준비 중에 만들어집니다. 포리스트 준비에 대 한 자세한 내용은 비즈니스용 Skype 용 Active Directory 도메인 서비스 서버용을 참조 하세요. 포리스트 준비로 만든 특정 그룹에 대 한 자세한 내용은 배포 설명서의 비즈니스용 Skype 서버에서 포리스트 준비에의 한 변경 내용을 참조 하세요.
ms.openlocfilehash: 41efad45b442d9c7fca82d090afa0d1aa23e7d63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815626"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>비즈니스용 Skype 서버용에 대 한 RBAC (역할 기반 액세스 제어)
 
비즈니스용 Skype 서버에는 관리 작업을 위임할 수 있는 RBAC (역할 기반 액세스 제어) 그룹이 포함 되어 있으며 보안에 대 한 높은 표준도 유지 됩니다. 이러한 그룹은 포리스트 준비 중에 만들어집니다. 포리스트 준비에 대 한 자세한 내용은 [비즈니스용 Skype 용 Active Directory 도메인 서비스 서버용](active-directory-domain-services.md)을 참조 하세요. 포리스트 준비로 만든 특정 그룹에 대 한 자세한 내용은 배포 설명서의 [비즈니스용 Skype 서버에서 포리스트 준비에의 한 변경 내용을](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 참조 하세요.
  
RBAC를 사용 하면 여러 일반적인 관리 작업을 처리 하는 11 개의 미리 정의 된 역할을 포함 하 여 사용자를 미리 정의한 관리 역할에 할당 하는 관리 권한이 부여 됩니다. 각 역할은 해당 역할의 사용자가 실행할 수 있는 비즈니스용 Skype Server Management Shell cmdlet의 특정 목록과 연결 되어 있습니다. RBAC를 사용 하 여 사용자에 게 해당 작업에 필요한 관리 기능만 제공 하는 "최소 권한"의 원칙을 따를 수 있습니다. 
  
RBAC 역할에 대 한 자세한 내용은 [역할 기반 액세스 제어에 대 한 계획](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)을 참조 하세요.
