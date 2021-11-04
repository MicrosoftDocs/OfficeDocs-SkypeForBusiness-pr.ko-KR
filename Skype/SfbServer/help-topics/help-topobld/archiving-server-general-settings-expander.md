---
title: 보관 서버 일반 설정 확장기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 토폴로지 작성기에서 콘솔 트리에서 보관을 실행 중인 서버를 마우스 오른쪽 단추로 클릭하고 도구 모음에서 동작을 클릭하거나 동작 창에서 작업을 클릭한 다음 속성 편집을 클릭하고 다음 옵션 중 하나를 변경하여 보관을 실행하는 개별 서버의 속성을 편집할 수 있습니다.
ms.openlocfilehash: c8537e661a5e2b854df144782977507b5e3a4f3f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768136"
---
# <a name="archiving-server-general-settings-expander"></a>보관 서버 일반 설정 확장기
 
토폴로지 작성기에서 콘솔 트리에서 보관을 실행 중인 서버를 마우스 오른쪽 단추로 클릭하고 도구 모음에서 동작을  클릭하거나 동작 창에서 작업을 클릭한 다음 속성 편집을 클릭하고 다음 옵션 중 하나를 변경하여 보관을 실행하는 개별 서버의 속성을 편집할 수 있습니다. 
  
- **FQDN**: 보관을 실행하는 서버로 배포할 서버의 FQDN(정규화된 도메인 이름)을 변경합니다.
    
- **SQL 저장소**: 보관 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스를 변경합니다. 보관을 실행 중인 서버의 SQL Server 데이터베이스를 변경하려면 보관을 실행 중인 서버를 다시 시작하여 변경 내용이 적용되도록 해야 합니다.
    
- **파일 저장소**: 보관 파일 저장소에 사용할 폴더를 변경합니다. 보관을 실행 중인 서버의 파일 저장소를 변경하려면 보관을 실행 중인 서버를 다시 시작하여 변경 내용이 적용되도록 해야 합니다. 또한 보관된 회의 파일이 손실되지 않도록 이전 회의 파일을 새 파일 저장소 폴더로 이동해야 합니다.
    
> [!NOTE]
> 보관을 실행 중인 서버와 연결된 풀을 변경하려면 현재 보관을 실행 중인 서버와 연결되어 있는 개별 프런트 엔드 풀 노드 또는 SBA(Survivable Branch Appliance) 노드에 대해 **속성 편집** 옵션을 선택합니다.
  
> [!NOTE]
> 토폴로지 작성기에서 이전에 보관을 실행 중인 서버를 토폴로지에 추가한 경우 보관 노드에 보관을 실행 중인 서버가 포함되어 있습니다. 목록에 있는 보관을 실행 중인 모든 서버의 속성을 편집할 수 있습니다. 그러나 보관을 실행 중인 서버에 대한 서비스도 설정할 때까지는 인스턴트 메시징 또는 웹 회의(메시징)를 보관할 수 없습니다. 
  

