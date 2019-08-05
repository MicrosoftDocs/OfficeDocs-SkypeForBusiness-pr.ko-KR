---
title: 단일 Standard Edition Server 준비(소개)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 중앙 관리 저장소와 다른 collocated 서비스를 보유 하는 비즈니스용 Skype Server 2015 Standard Edition server의 설치를 시작 하려면 서버에서 로컬 관리자 그룹의 구성원으로 로그인 해야 합니다. 스탠더드 버전 서버가 됩니다. 단일 Standard Edition Server 준비 페이지에 처음 설치에 대한 요구 사항이 자세히 나와 있습니다. 컴퓨터는 서버를 배포할 도메인의 구성원이어야 하며 사용자는 포리스트에 대한 스키마, 포리스트 및 도메인 준비를 성공적으로 완료해야 합니다.
ms.openlocfilehash: cb8e370adc13d30d320aceb70218115991592257
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189597"
---
# <a name="prepare-single-standard-edition-server-intro"></a>단일 Standard Edition Server 준비(소개)
 
중앙 관리 저장소와 다른 collocated 서비스를 보유 하는 비즈니스용 Skype Server 2015 Standard Edition server의 설치를 시작 하려면 서버에서 로컬 관리자 그룹의 구성원으로 로그인 해야 합니다. 스탠더드 버전 서버가 됩니다. **단일 Standard Edition Server 준비** 페이지에 처음 설치에 대한 요구 사항이 자세히 나와 있습니다. 컴퓨터는 서버를 배포할 도메인의 구성원이어야 하며 사용자는 포리스트에 대한 스키마, 포리스트 및 도메인 준비를 성공적으로 완료해야 합니다.
  
이 특정 작업은 Standard Edition 서버를 인프라의 첫 번째 서버로 설치하도록 디자인되었습니다. 이 작업은 중앙 관리 저장소 (SQL Server Express)를 Standard Edition 서버에 설치 합니다. 이미 다른 Standard Edition 서버 또는 프런트 엔드 풀을 배포한 경우 **취소**를 클릭해야 합니다.
  
> [!NOTE]
> 이 작업을 완료 한 후에는 토폴로지 작성기를 설치 하 고 (아직 설치 하지 않은 경우) 토폴로지 문서를 구성 합니다. 이 항목에서 설명하는 작업을 완료하여 배포하는 중앙 관리 저장소가 사용 가능해질 때까지 토폴로지 문서를 게시할 수 없습니다. 
  

