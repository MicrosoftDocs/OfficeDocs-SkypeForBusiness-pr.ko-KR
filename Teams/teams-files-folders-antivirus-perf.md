---
title: 바이러스 백신 검색에서 제외할 Teams 파일 및 폴더
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 일반 바이러스 검사에서 특정 파일 및 폴더를 제외 하 여 팀의 성과를 향상 시킵니다.
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579594"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>바이러스 백신 검색에서 제외할 Teams 파일 및 폴더
=================================

바이러스 백신 프로그램이 특정 팀 파일 및 폴더를 검색 하지 못하도록 하 여 팀 배포의 전반적인 성능을 향상 시킬 수 있습니다. 이렇게 하면 검색할 필요가 없는 파일 및 폴더를 검색 하는 시스템 리소스의 비용을 피할 수 있습니다.

> [!NOTE]
> 사용자가 파일을 다운로드 하거나 파일을 공유 하는 경우, 해당 파일은 다음 섹션에 나열 된 위치를 통과 하지 못합니다. 사용자가 업로드, 다운로드 또는 파일을 공유 하는 위치는 여전히 바이러스 백신 프로그램에서 정기적으로 검색 합니다.

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>바이러스 백신 수신 허용 목록에 추가할 파일 및 폴더

바이러스 백신 프로그램에서 지원 되는 절차를 사용 하 여 다음 파일 및 폴더를 수신 허용 목록에 추가 합니다. 이렇게 하면 이러한 위치에 대 한 바이러스 백신 검사를 방지 하 여 시스템 리소스를 절약할 수 있습니다.

### <a name="programs"></a>프로그램이

바이러스 백신 수신 허용 목록에 다음 팀 프로그램을 추가 합니다.

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

