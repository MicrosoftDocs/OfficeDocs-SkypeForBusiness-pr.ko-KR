---
title: 단일 Standard Edition Server 준비(소개)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 중앙 관리 저장소 및 선택한 다른 함께 사용 서비스를 보유할 비즈니스용 Skype 서버 2015 Standard Edition 서버의 설치를 시작하려면 Standard Edition 서버가 될 서버에서 로컬 Administrators 그룹의 구성원으로 로그인해야 합니다. 단일 Standard Edition Server 준비 페이지에 처음 설치에 대한 요구 사항이 자세히 나와 있습니다. 컴퓨터는 서버를 배포할 도메인의 구성원이어야 하며 사용자는 포리스트에 대한 스키마, 포리스트 및 도메인 준비를 성공적으로 완료해야 합니다.
ms.openlocfilehash: daca3f64809b6ea6d2ed5e94cdaf3a38ebef6f4d9ba75885b6d6d0aff50ecfd3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313526"
---
# <a name="prepare-single-standard-edition-server-intro"></a>단일 Standard Edition Server 준비(소개)
 
중앙 관리 저장소 및 선택한 다른 함께 사용 서비스를 보유할 비즈니스용 Skype 서버 2015 Standard Edition 서버의 설치를 시작하려면 Standard Edition 서버가 될 서버에서 로컬 Administrators 그룹의 구성원으로 로그인해야 합니다. **단일 Standard Edition Server 준비** 페이지에 처음 설치에 대한 요구 사항이 자세히 나와 있습니다. 컴퓨터는 서버를 배포할 도메인의 구성원이어야 하며 사용자는 포리스트에 대한 스키마, 포리스트 및 도메인 준비를 성공적으로 완료해야 합니다.
  
이 특정 작업은 Standard Edition 서버를 인프라의 첫 번째 서버로 설치하도록 디자인되었습니다. 이 작업은 중앙 관리 저장소(SQL Server Express)를 Standard Edition 설치합니다. 이미 다른 Standard Edition 서버 또는 프런트 엔드 풀을 배포한 경우 **취소** 를 클릭해야 합니다.
  
> [!NOTE]
> 이 작업을 완료한 후 토폴로지 작성기(아직 설치하지 않은 경우)를 설치하고 토폴로지 문서를 구성합니다. 이 항목에서 설명하는 작업을 완료하여 배포하는 중앙 관리 저장소가 사용 가능해질 때까지 토폴로지 문서를 게시할 수 없습니다. 
  

