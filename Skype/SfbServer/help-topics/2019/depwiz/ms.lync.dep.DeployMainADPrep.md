---
title: Active Directory 준비
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: 비즈니스용 Skype 서버 설치를 시작 하려면 서버와 사용자를 호스트할 Active Directory 도메인 서비스 스키마, 포리스트 및 도메인을 준비 해야 합니다. 비즈니스용 Skype 서버 배포 마법사는 스키마부터 시작 하 여 포리스트 준비로 이동 하 여 Active Directory를 준비 하는 데 필요한 단계를 안내 합니다. Active Directory 복제가 성공 했는지 확인 한 후에는 사용자 또는 서버를 호스트할 각 도메인을 준비 합니다.
ms.openlocfilehash: 1cb997223a9f613bac4aeeec45d3a029d4436e18
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691863"
---
# <a name="prepare-active-directory"></a>Active Directory 준비

비즈니스용 Skype 서버 설치를 시작 하려면 서버와 사용자를 호스트할 Active Directory 도메인 서비스 스키마, 포리스트 및 도메인을 준비 해야 합니다. 비즈니스용 Skype 서버 배포 마법사는 스키마부터 시작 하 여 포리스트 준비로 이동 하 여 Active Directory를 준비 하는 데 필요한 단계를 안내 합니다. Active Directory 복제가 성공 했는지 확인 한 후에는 사용자 또는 서버를 호스트할 각 도메인을 준비 합니다.

> [!IMPORTANT]
> 스키마를 성공적으로 준비하려면 Enterprise Admins 그룹 및 Schema Admins 그룹의 구성원으로 로그인해야 합니다. 포리스트를 준비하려면 Enterprise Admins 그룹의 구성원으로 로그인하거나 포리스트 루트에서 관리자로 로그인해야 합니다. 도메인 준비를 위해서는 Domain Admins 그룹의 구성원으로 로그인해야 합니다.

지원되는 Active Directory 토폴로지에 대한 자세한 내용은 지원 가능성 설명서에서 [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)을 참조하세요. Active Directory 준비에 대한 자세한 내용은 배포 설명서에서 [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)를 참조하세요.


