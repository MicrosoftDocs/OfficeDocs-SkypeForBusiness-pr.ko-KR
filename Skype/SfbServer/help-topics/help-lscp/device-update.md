---
title: 장치 업데이트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: 'Microsoft는 비즈니스용 Skype Phone 에디션에 대 한 새로운 디바이스 펌웨어 업데이트 집합을 정기적으로 릴리스 하 여 서버로 가져오고 사용자에 게 배포할 수 있습니다. Microsoft 웹 사이트의 도움말 및 지원 페이지로 이동 하 여 forPhone Edition을 검색 하 여 최신 장치 업데이트 규칙 집합을 구할 수 있습니다. 최신 업데이트 패키지를 다운로드 하 고 업데이트를 업로드할 컴퓨터의 폴더에 파일 압축을 풉니다. 파일이 추출되면 Import-CsDeviceUpdate cmdlet을 사용하여 추출된 .CAB 파일(예: UCUpdates.cab)에 있는 장치 업데이트 규칙을 가져올 수 있습니다. 자세한 내용은 가져오기-CsDeviceUpdate를 참조 하세요.'
ms.openlocfilehash: b387a24d88ab0b65c3df43a8ca5dd25d582a4827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190275"
---
# <a name="device-update"></a>장치 업데이트

Microsoft는 비즈니스용 Skype Phone 에디션에 대 한 새로운 디바이스 펌웨어 업데이트 집합을 정기적으로 릴리스 하 여 서버로 가져오고 사용자에 게 배포할 수 있습니다. Microsoft 웹 사이트의 도움말 및 지원 페이지로 이동하여 "Phone Edition"을 검색하면 최신 장치 업데이트 규칙 집합을 가져올 수 있습니다. 최신 업데이트 패키지를 다운로드하고, 업데이트를 업로드할 컴퓨터의 폴더에 파일을 추출합니다. 파일이 추출되면 **Import-CsDeviceUpdate** cmdlet을 사용하여 추출된 .CAB 파일(예: UCUpdates.cab)에 있는 장치 업데이트 규칙을 가져올 수 있습니다. 자세한 내용은 [가져오기-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)를 참조 하세요.

장치 업데이트 규칙을 가져온 후 **장치 업데이트** 페이지를 사용 하 여 조직의 디바이스에 대 한 이러한 규칙을 보고 관리할 수 있습니다.

> [!TIP]
> 펌웨어 업데이트를 테스트한 다음 테스트에 성공하면 조직에서 사용 중인 모든 관련 장치에 업데이트를 적용할 수 있습니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**장치 업데이트** 페이지에서는 다음 작업을 수행할 수 있습니다.

- 목록의 장치 업데이트 승인

- 대기 중인 장치 업데이트 취소 또는 복원

- 목록에서 장치 업데이트 삭제

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.

- **편집** 이 옵션을 사용 하 여 다음을 수행할 수 있습니다.

  - **모두 선택** 이 옵션은 목록의 모든 장치 업데이트를 선택 합니다.

  - **삭제** 이 옵션은 선택한 모든 장치 업데이트를 삭제 합니다.

- **작업** 목록에서 하나 이상의 업데이트를 선택 하 고 다음 작업을 수행할 수 있습니다.

  - **보류 중인 업데이트 취소** 이 옵션을 선택 하면 선택한 업데이트가 조직의 장치에 배포 되지 않습니다.

  - **승인** 이 옵션을 선택 하면 선택한 업데이트가 조직의 장치에 배포 됩니다.

  - **복원** 이 옵션을 사용 하면 이전에 승인 된 업데이트를 조직의 장치에 배포할 수 있습니다.

- **새로 고침** 목록을 새로 고쳐 모든 장치 업데이트의 상태를 확인할 수 있습니다.

장치 업데이트 웹 서비스에 대한 자세한 내용은 계획 설명서에서 [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)를 참조하세요.
## <a name="see-also"></a>참고 항목

[가져오기-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
