---
title: Active Directory 준비
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: 설치 비즈니스용 Skype 서버 서버 및 사용자를 호스팅할 Active Directory 도메인 서비스, 포리스트 및 도메인을 준비해야 합니다. 비즈니스용 Skype 서버 배포 마법사는 Active Directory를 준비하는 데 필요한 단계를 안내합니다. 이 단계에서는 이 과정부터 시작하여 포리스트 준비에 대해 설명합니다. Active Directory 복제가 성공적이면 사용자 또는 서버를 호스팅할 각 도메인을 준비합니다.
ms.openlocfilehash: 082c80e4ee611a524f99919c744a2a1f49e2719d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578022"
---
# <a name="prepare-active-directory"></a>Active Directory 준비

설치 비즈니스용 Skype 서버 서버 및 사용자를 호스팅할 Active Directory 도메인 서비스, 포리스트 및 도메인을 준비해야 합니다. 비즈니스용 Skype 서버 배포 마법사는 Active Directory를 준비하는 데 필요한 단계를 안내합니다. 이 단계에서는 이 과정부터 시작하여 포리스트 준비에 대해 설명합니다. Active Directory 복제가 성공적이면 사용자 또는 서버를 호스팅할 각 도메인을 준비합니다.

> [!IMPORTANT]
> 스키마를 성공적으로 준비하려면 Enterprise Admins 그룹 및 Schema Admins 그룹의 구성원으로 로그인해야 합니다. 포리스트를 준비하려면 Enterprise Admins 그룹의 구성원으로 로그인하거나 포리스트 루트에서 관리자로 로그인해야 합니다. 도메인 준비를 위해서는 Domain Admins 그룹의 구성원으로 로그인해야 합니다.

지원되는 Active Directory 토폴로지에 대한 자세한 내용은 지원 가능성 설명서에서 [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support)을 참조하십시오. Active Directory 준비에 대한 자세한 내용은 배포 설명서에서 [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation)를 참조하십시오.