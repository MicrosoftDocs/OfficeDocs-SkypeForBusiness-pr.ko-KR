---
title: 보관 서버 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 토폴로지 작성기의 콘솔 트리에서 보관을 실행 중인 서버를 마우스 오른쪽 단추로 클릭하고 도구 모음에서 동작을 클릭하거나 동작 창에서 작업을 클릭한 다음 속성 편집을 클릭하고 다음 옵션 중에서 원하는 옵션을 변경하여 보관을 실행 중인 개별 서버의 속성을 편집할 수 있습니다.
ms.openlocfilehash: 4a838b6b6246ae99de7ff5ff3d84603a0f25c2ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820490"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="a49e5-103">보관 서버 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="a49e5-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="a49e5-104">토폴로지 작성기의 콘솔 트리에서 보관을 실행 중인 서버를 마우스 오른쪽 단추로 클릭하고 도구 모음에서 **동작**을 클릭하거나 동작 창에서 작업을 클릭한 다음 **속성 편집**을 클릭하고 다음 옵션 중에서 원하는 옵션을 변경하여 보관을 실행 중인 개별 서버의 속성을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a49e5-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="a49e5-105">**FQDN**: 보관을 실행하는 서버로 배포할 서버의 FQDN(정규화된 도메인 이름)을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a49e5-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="a49e5-p101">**SQL 저장소**: 보관 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스를 변경합니다. 보관을 실행 중인 서버의 SQL Server 데이터베이스를 변경하려면 보관을 실행 중인 서버를 다시 시작하여 변경 내용이 적용되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a49e5-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="a49e5-p102">**파일 공유**: 보관 파일 저장소에 사용할 폴더를 변경합니다. 보관을 실행 중인 서버의 파일 저장소를 변경하려면 보관을 실행 중인 서버를 다시 시작하여 변경 내용이 적용되도록 해야 합니다. 또한 보관된 회의 파일이 손실되지 않도록 이전 회의 파일을 새 파일 저장소 폴더로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a49e5-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a49e5-111">보관을 실행 중인 서버와 연결된 풀을 변경하려면 현재 보관을 실행 중인 서버와 연결되어 있는 개별 프런트 엔드 풀 노드 또는 SBA(Survivable Branch Appliance) 노드에 대해 **속성 편집** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a49e5-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a49e5-p103">토폴로지 작성기에서 이전에 보관을 실행 중인 서버를 토폴로지에 추가한 경우 보관 노드에 보관을 실행 중인 서버가 포함되어 있습니다. 목록에 있는 보관을 실행 중인 모든 서버의 속성을 편집할 수 있습니다. 그러나 보관을 실행 중인 서버에 대해 서비스도 설정할 때까지는 메신저 대화 또는 웹 회의(메시징)는 보관할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a49e5-p103">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder. You can edit properties for any server running Archiving in the list. However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

