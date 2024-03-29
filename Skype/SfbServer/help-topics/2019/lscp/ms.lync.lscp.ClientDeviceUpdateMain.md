---
title: 장치 업데이트
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: 'NOINDEX, NOFOLLOW'
description: Microsoft는 서버로 가져와서 사용자에게 배포할 수 있는 비즈니스용 Skype 전화 Edition에 대한 새로운 장치 펌웨어 업데이트 집합을 주기적으로 출시합니다. Microsoft 웹 사이트의 도움말 및 지원 페이지로 이동하고Phone Edition을 검색하여 최신 장치 업데이트 규칙 집합을 얻을 수 있습니다.최신 업데이트 패키지를 다운로드하고 업데이트를 업로드할 컴퓨터의 폴더에 파일을 추출합니다. 파일을 추출한 후 Import-CsDeviceUpdate cmdlet을 사용하여 추출된 .CAB 파일에 있는 장치 업데이트 규칙을 가져올 수 있습니다(이름이 UCUpdates.cab). 자세한 내용은 Import-CsDeviceUpdate를 참조합니다.
---

# <a name="device-update"></a>장치 업데이트

Microsoft는 서버로 가져와서 사용자에게 배포할 수 있는 비즈니스용 Skype 전화 Edition에 대한 새로운 장치 펌웨어 업데이트 집합을 주기적으로 출시합니다. Microsoft 웹 사이트의 도움말 및 지원 페이지로 이동하고 "전화 Edition"을 검색하여 최신 장치 업데이트 규칙 집합을 얻을 수 있습니다. 최신 업데이트 패키지를 다운로드하고 업데이트를 업로드할 컴퓨터의 폴더에 파일을 추출합니다. 파일을 추출한 후 **Import-CsDeviceUpdate** cmdlet을 사용하여 추출된 .CAB 파일에 있는 장치 업데이트 규칙을 가져올 수 있습니다(이름이 UCUpdates.cab). 자세한 내용은 [Import-CsDeviceUpdate를 참조합니다](/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

장치 업데이트 규칙을 가져온 후 장치 업데이트 페이지를 사용하여 조직의 장치에 대한 이러한 규칙을  보고 관리할 수 있습니다.

> [!TIP]
> 펌웨어 업데이트를 테스트한 다음 테스트가 성공한 경우 조직에서 사용되는 모든 관련 장치에서 업데이트를 사용할 수 있도록 할 수 있습니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

장치 업데이트 페이지에서는 다음 **작업을 수행할 수** 있습니다.

- 목록에서 장치 업데이트를 승인합니다.

- 보류 중인 장치 업데이트를 취소하거나 복원합니다.

- 목록에서 장치 업데이트를 삭제합니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

- **편집** 이 옵션을 사용하여 다음을 할 수 있습니다.

  - **모두 선택** 이 옵션은 목록의 모든 장치 업데이트를 선택합니다.

  - **삭제** 이 옵션은 선택한 모든 장치 업데이트를 삭제합니다.

- **작업** 목록에서 업데이트를 하나 이상 선택하고 다음 작업을 수행할 수 있습니다.

  - **보류 중인 업데이트 취소** 이 옵션을 사용하면 선택한 업데이트가 조직의 장치에 배포되지 않습니다.

  - **승인** 이 옵션을 사용하면 선택한 업데이트를 조직의 장치에 배포할 수 있습니다.

  - **복원** 이 옵션을 사용하면 이전에 승인된 업데이트를 조직의 장치에 배포할 수 있습니다.

- **새로 고침** 목록을 새로 고쳐 모든 장치 업데이트의 상태를 확인할 수 있습니다.

장치 업데이트 웹 서비스에 대한 자세한 내용은 계획 설명서에서 [View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization) 를 참조하십시오.
## <a name="see-also"></a>참고 항목

[Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)