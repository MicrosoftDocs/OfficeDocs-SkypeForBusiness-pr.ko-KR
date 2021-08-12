---
title: 사용자용 RBAC(역할 기반 액세스 제어) 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 비즈니스용 Skype 서버 RBAC(Role-Based 액세스 제어) 그룹을 포함하면 보안에 대한 높은 표준을 유지하면서 관리 작업을 위임할 수 있습니다. 이러한 그룹은 포리스트 준비 중에 만들어집니다. 포리스트 준비에 대한 자세한 내용은 Active Directory Domain Services for 비즈니스용 Skype 서버. 포리스트 준비로 만든 특정 그룹에 대한 자세한 내용은 배포 설명서의 비즈니스용 Skype 서버 포리스트 준비로 변경을 참조하십시오.
ms.openlocfilehash: 8b4dbfc85a92063bff7e5c57ee18ccc9b80bb4e08b0716fd1cac0666f1862fb0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337726"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>사용자용 RBAC(역할 기반 액세스 제어) 비즈니스용 Skype 서버
 
비즈니스용 Skype 서버 RBAC(Role-Based 액세스 제어) 그룹을 포함하면 보안에 대한 높은 표준을 유지하면서 관리 작업을 위임할 수 있습니다. 이러한 그룹은 포리스트 준비 중에 만들어집니다. 포리스트 준비에 대한 자세한 내용은 [Active Directory Domain Services for 비즈니스용 Skype 서버.](active-directory-domain-services.md) 포리스트 준비로 만든 특정 그룹에 대한 [](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 자세한 내용은 배포 설명서의 비즈니스용 Skype 서버 포리스트 준비로 변경을 참조하십시오.
  
RBAC를 사용하는 경우 대부분의 일반 관리 작업을 포함하는 11개의 미리 정의된 역할을 포함하여 사용자를 미리 정의된 관리 역할에 할당하여 관리 권한을 부여합니다. 각 역할은 해당 역할의 사용자가 비즈니스용 Skype 서버 관리 셸 cmdlet의 특정 목록과 연결됩니다. RBAC를 사용하여 사용자에게 작업에 필요한 관리 기능만 제공되는 "최소 권한" 원칙을 따를 수 있습니다. 
  
RBAC 역할에 대한 자세한 내용은 역할 기반 액세스 제어 계획 [에서 찾을 수 있습니다.](/lyncserver/lync-server-2013-planning-for-role-based-access-control)