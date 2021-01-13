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
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: 비즈니스용 Skype 서버 설치를 시작하려면 서버 및 사용자를 호스팅할 Active Directory 도메인 서비스, 포리스트 및 도메인을 준비해야 합니다. 비즈니스용 Skype 서버 배포 마법사는 Active Directory를 준비하는 데 필요한 단계를 안내하며, 이 단계를 시작하여 포리스트 준비에 대해 안내합니다. Active Directory 복제가 성공적이면 사용자 또는 서버를 호스팅할 각 도메인을 준비합니다.
ms.openlocfilehash: 4e2951643ddc0f569df6802b6ff5fdd8d2c12a82
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825054"
---
# <a name="prepare-active-directory"></a>Active Directory 준비

비즈니스용 Skype 서버 설치를 시작하려면 서버 및 사용자를 호스팅할 Active Directory 도메인 서비스, 포리스트 및 도메인을 준비해야 합니다. 비즈니스용 Skype 서버 배포 마법사는 Active Directory를 준비하는 데 필요한 단계를 안내하며, 이 단계를 시작하여 포리스트 준비에 대해 안내합니다. Active Directory 복제가 성공적이면 사용자 또는 서버를 호스팅할 각 도메인을 준비합니다.

> [!IMPORTANT]
> 스키마를 성공적으로 준비하려면 Enterprise Admins 그룹 및 Schema Admins 그룹의 구성원으로 로그인해야 합니다. 포리스트를 준비하려면 Enterprise Admins 그룹의 구성원으로 로그인하거나 포리스트 루트에서 관리자로 로그인해야 합니다. 도메인 준비를 위해서는 Domain Admins 그룹의 구성원으로 로그인해야 합니다.

지원되는 Active Directory 토폴로지에 대한 자세한 내용은 지원 가능성 설명서에서 [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)을 참조하십시오. Active Directory 준비에 대한 자세한 내용은 배포 설명서에서 [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)를 참조하십시오.


