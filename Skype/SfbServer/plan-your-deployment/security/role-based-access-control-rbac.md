---
title: 비즈니스용 Skype 서버용 RBAC(역할 기반 액세스 제어)
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
description: 비즈니스용 Skype 서버에는 보안에 Role-Based 높은 표준을 유지하면서 관리 작업을 위임할 수 있는 RBAC(액세스 제어) 그룹이 포함되어 있습니다. 이러한 그룹은 포리스트 준비 중에 만들어집니다. 포리스트 준비에 대한 자세한 내용은 비즈니스용 Skype 서버용 Active Directory 도메인 서비스를 참조하십시오. 포리스트 준비로 만든 특정 그룹에 대한 자세한 내용은 배포 설명서에서 비즈니스용 Skype 서버의 포리스트 준비에서 변경한 내용을 참조하십시오.
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832108"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>비즈니스용 Skype 서버용 RBAC(역할 기반 액세스 제어)
 
비즈니스용 Skype 서버에는 보안에 Role-Based 높은 표준을 유지하면서 관리 작업을 위임할 수 있는 RBAC(액세스 제어) 그룹이 포함되어 있습니다. 이러한 그룹은 포리스트 준비 중에 만들어집니다. 포리스트 준비에 대한 자세한 내용은 비즈니스용 [Skype 서버용 Active Directory 도메인 서비스를 참조하십시오.](active-directory-domain-services.md) 포리스트 준비로 만든 특정 그룹에 대한 자세한 내용은 배포 설명서에서 비즈니스용 Skype 서버의 포리스트 [준비에서 변경한](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 내용을 참조하십시오.
  
RBAC를 사용하는 경우 대부분의 일반 관리 작업을 포함하는 11개의 미리 정의된 역할을 포함하여 사용자를 미리 정의된 관리 역할에 할당하여 관리 권한을 부여합니다. 각 역할은 해당 역할의 사용자가 실행할 수 있는 비즈니스용 Skype 서버 관리 셸 cmdlet의 특정 목록과 연결됩니다. RBAC를 사용하여 사용자에게 작업에 필요한 관리 기능만 제공되는 "최소 권한" 원칙을 따를 수 있습니다. 
  
RBAC 역할에 대한 자세한 내용은 역할 기반 액세스 제어 [계획에서 찾을 수 있습니다.](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)
