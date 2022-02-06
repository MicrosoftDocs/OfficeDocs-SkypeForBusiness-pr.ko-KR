---
title: 사용자 계정 관리 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: '이 문서의 섹션에서는 Active Directory 사용자 사용, 일시적 사용 안 하도록 설정 또는 제거 하는 방법을 설명 하는 비즈니스용 Skype 서버.'
---

# <a name="manage-user-accounts-for-skype-for-business-server"></a>사용자 계정 관리 비즈니스용 Skype 서버

이 문서의 섹션에서는 Active Directory 사용자 사용, 일시적 사용 안 하도록 설정 또는 제거 하는 방법을 설명 하는 비즈니스용 Skype 서버.

Active Directory 사용자를 사용하도록 설정하는 방법에 대한 자세한 내용은 [Create a New User Account를 참조하십시오](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)). Active Directory 사용자를 삭제하는 방법에 대한 자세한 내용은 [Delete a User Account를 참조하십시오](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).

이러한 절차는 사용률이 가장 낮은 경우 유지 관리 기간 비즈니스용 Skype 수행해야 합니다. 이 수행 여부는 조직의 요구에 따라 결정됩니다.

이 문서에는 다음 절차가 포함되어 있습니다.

- [한명 이상의 사용자 검색](#search-for-one-or-more-users)

- [새 사용자 추가 및 비즈니스용 Skype 서버 사용](#add-and-enable-a-new-skype-for-business-server-user)

- [사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 비즈니스용 Skype 서버](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

- [사용자를 사용하지 않도록 Enterprise Voice](#disable-a-user-for-enterprise-voice)

- [관리 셸을 사용하여 사용자 비즈니스용 Skype 서버 제거](#remove-a-user-account-with-the-skype-for-business-server-management-shell)

## <a name="search-for-one-or-more-users"></a>한명 이상의 사용자 검색

검색 쿼리의 결과를 사용하여 검색 쿼리에 대해 Active Directory 사용자를 구성할 수 비즈니스용 Skype 서버. 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)로 사용자를 검색할 수 있습니다.

비즈니스용 Skype 서버 Active Directory 사용자 및 컴퓨터 스냅인을 사용하여 사용자를 검색할 수 있습니다. 다음 절차에서는 제어판을 사용하여 사용자를 비즈니스용 Skype 서버 방법을 설명합니다.

> [!NOTE]
> 중앙 포리스트 토폴로지가 있는 환경에서는 사용자의 전자 메일 주소로 사용자를 검색할 때 검색 결과가 정확하지 않을 수 있습니다. 이러한 경우에는 sip:name과 같은 SIP 주소 접두사를 지정하여 사용자를 검색하거나, 검색 필터를 추가하고 전자 메일 주소의 일부분이 포함된 SIP 주소를 선택하거나, **Get-CSUser** cmdlet을 사용할 수 있습니다.

### <a name="search-for-users-using-the-new-control-panel"></a>새 제어판을 사용하여 사용자 검색 

1. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.
 
2. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정을 사용하여 로그인합니다.

3. 왼쪽 창에서 사용자를 **선택합니다**.

4. 사용자 **페이지의** 검색 상자에 검색할  표시 이름의 전체 또는 첫 부분을 입력하고 **Enter를 클릭합니다**.

5. (선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.

    1. 검색 상자 옆에 있는 필터 **단추를** 클릭합니다.

    2. 필터 **패널** 이 나타나면 드롭다운 목록에서 화살표를 클릭하여 필요한 사용자 속성을 선택합니다.

    3. 드롭다운 연산자 목록에서 화살표를 클릭하여 필요한 연산자를 선택합니다.

    4. 텍스트 상자에 검색 결과를 필터링하는 데 사용할 검색 조건을 입력하고 확인을 **클릭합니다**.

6. 검색 결과가 사용자 **페이지에 표시됩니다.** 목록에서 원하는 사용자 또는 모든 사용자를 선택하고 선택한 사용자에 대해 구성 작업을 수행할 수 있습니다.

> [!NOTE]
> 2015년 8월에는 새 제어판을 비즈니스용 Skype 서버 없습니다.

### <a name="search-for-users-using-the-legacy-control-panel"></a>레거시 제어판을 사용하여 사용자 검색 

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.

3. 왼쪽 창에서 사용자를 **선택합니다**.

4. **사용자 검색** 상자에 검색할 사용자 계정의 표시 이름, 이름, 성, SAM 계정 이름, SIP 주소 또는 줄 URI를 모두 입력하거나 첫 부분을 입력하고 **찾기** 를 클릭합니다.

5. (선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.

    1. 화면 오른쪽 위의 **검색 결과** 위에 있는 확장 화살표 단추를 클릭하고 **필터 추가** 를 클릭합니다.

    2. 사용자 속성을 입력하거나 드롭다운 목록에서 화살표를 클릭하여 사용자 속성을 선택합니다.

    3. 같 **음 목록** 에서 같음 또는  같 **지 않습니다를 선택합니다**.

    4. 텍스트 상자에 검색 결과를 필터링하는 데 사용할 검색 조건을 입력하고 **찾기** 를 입력합니다.

6. **검색 결과** 아래에 검색 결과가 나타납니다. 목록에서 원하는 사용자 또는 모든 사용자를 선택하고 선택한 사용자에 대해 구성 작업을 수행할 수 있습니다.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>새 사용자 추가 및 비즈니스용 Skype 서버 사용

Active Directory 사용자 및 컴퓨터에서 사용자 계정을 사용하도록 설정한 후 비즈니스용 Skype 서버 제어판을 사용하여 Active Directory 사용자를 추가하여 새 비즈니스용 Skype 서버 사용자 계정을 만들고 사용하도록 설정할 수 비즈니스용 Skype 서버.

특히 [Enable-CsUser](/powershell/module/skype/enable-csuser)와 같은 cmdlet을 사용할 수 있습니다.

### <a name="add-a-user-using-the-new-control-panel"></a>새 제어판을 사용하여 사용자 추가 

1. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.
 
2. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정을 사용하여 로그인합니다.

3.  > **UsersEnable Users로 이동** 한 다음 추가를 **클릭합니다**.

4. 검색 **상자** 에 표시 이름의 전체 또는 첫 번째 부분을 입력하고 찾기를 **클릭합니다**.

5. (선택 사항) 추가 사용자 조건을 지정하려면 **+** 필터 추가를 클릭하고 필요한 사용자 속성을 선택하고 연산자를 선택한 다음 값을 입력합니다. **찾기** 를 클릭합니다.

6. 표에서 추가하려는 계정을 비즈니스용 Skype 서버 확인을 **클릭합니다**.

7. 사용자를 풀에 할당하고 추가 세부 정보를 지정한 다음 필요한 정책을 사용자에게 할당한 다음 사용 을 **클릭합니다**.

> [!NOTE]
> 2015년 8월에는 새 제어판을 비즈니스용 Skype 서버 없습니다.

### <a name="add-a-user-using-the-legacy-control-panel"></a>레거시 제어판을 사용하여 사용자 추가 

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.

3.  > **UsersEnable usersNew** >  **Lync Server 사용자로 이동** 한 후 추가를 **클릭합니다.**

6. **사용자 검색** 상자에 원하는 Active Directory 사용자 계정의 이름, 표시 이름, 성, SAM(보안 계정 관리자) 계정 이름, 전자 메일 주소, UPN(사용자 계정 이름) 또는 전화 번호를 모두 또는 일부분 입력하고 **찾기** 를 클릭합니다.

7. 표에서 추가하려는 계정을 비즈니스용 Skype 서버 확인을 **클릭합니다**.

8. 풀에 사용자를 할당하고, 세부 정보를 추가로 지정하고, 원하는 사용자에게 정책을 할당한 후에 **사용** 을 클릭합니다.

## <a name="disable-or-re-enable-a-user-account-for-skype-for-business-server"></a>사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 비즈니스용 Skype 서버

다음 절차에 따라 사용자 계정에 대해 구성한 비즈니스용 Skype 서버 설정은 잃지 않고 이전에 사용하도록 설정된 사용자 계정을 비즈니스용 Skype 서버 수 있습니다. 사용자 계정 비즈니스용 Skype 서버 손실되지 않으면서 사용자 계정을 다시 구성하지 않고 이전에 사용하도록 설정한 사용자 계정을 다시 사용하도록 설정할 수 있습니다.

### <a name="disable-or-re-enable-a-user-account-using-the-new-control-panel"></a>새 제어판을 사용하여 사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 설정

1. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.
 
2. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정을 사용하여 로그인합니다.

3. 왼쪽 창에서 사용자를 **선택합니다**.

4. 사용자 **페이지의** 검색 상자에 표시 이름  의 전체 또는 첫 부분을 입력하고 **Enter를 클릭합니다**.

5. 표에서 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정을 두 번 클릭합니다.
    1. 나타나는 패널에서 사용자의 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 비즈니스용 Skype 서버 **사용 안 하도록 선택합니다**. 패널이 나타나면 저장을 **클릭합니다**.
    2. 사용자 계정을 다시 사용하도록 비즈니스용 Skype 서버 패널에서 사용자 다시 활성화 **를 선택합니다**. 다음 패널이 나타나면 저장을 **클릭합니다**.

> [!NOTE]
> 2015년 8월에는 새 제어판을 비즈니스용 Skype 서버 없습니다.

### <a name="disable-or-re-enable-a-user-account-using-the-legacy-control-panel"></a>레거시 제어판을 사용하여 사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 설정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.

3. 왼쪽 창에서 사용자를 **선택합니다**.

4. **사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기** 를 클릭합니다.

5. 표에서 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정을 클릭합니다.

6. **동작** 메뉴에서 다음 중 하나를 수행합니다.
   1. 사용자 계정의 사용자 계정을 비즈니스용 Skype 서버 **Lync Server** 에 대해 일시적으로 사용하지 않도록 설정을 선택합니다.
   2. 사용자 계정을 사용하도록 설정하려면 비즈니스용 Skype 서버 **Lync Server** 에 대해 다시 사용하도록 설정을 선택합니다.
  
### <a name="disable-or-re-enable-user-accounts-using-windows-powershell"></a>사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 Windows PowerShell

**Set-CsUser** cmdlet을 사용하여 사용자 계정을 일시적으로 사용하지 않도록 설정한 다음 나중에 다시 사용하도록 설정할 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 사용하여 서버에 연결하는 비즈니스용 Skype 서버 [자세한 내용은 Microsoft Lync Remote PowerShell Administration을 참조합니다](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). 프로세스는 동일한 비즈니스용 Skype 서버.

### <a name="to-disable-a-user-account-using-windows-powershell"></a>사용자 계정을 사용하지 않도록 설정하려면 다음을 Windows PowerShell

- 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 enabled 속성의 값을 False($False. 예제:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account-using-windows-powershell"></a>사용자 계정을 다시 사용하도록 설정하려면 다음을 Windows PowerShell

- 사용하지 않도록 설정된 사용자 계정을 다시 사용하도록 설정하려면 enabled 속성의 값을 True($True. 예제:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

자세한 내용은 [Set-CsUser](/powershell/module/skype/set-csuser) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="disable-a-user-for-enterprise-voice"></a>사용자를 사용하지 않도록 Enterprise Voice

다음 절차에 따라 Enterprise Voice 사용하도록 설정된 사용자 계정에 대해 이 설정을 사용하지 않도록 비즈니스용 Skype 서버.

### <a name="disable-a-user-for-enterprise-voice-using-new-control-panel"></a>사용자가 새 제어판을 Enterprise Voice 사용하지 않도록 설정

1. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.
 
2. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정을 사용하여 로그인합니다.

3. 왼쪽 창에서 사용자를 **클릭합니다**.

4. 검색 **상자** 에 표시 이름의 전체 또는 첫 번째 부분을 입력하고 찾기를 **클릭합니다**.

5. 표에서 사용자 계정에서 사용하지 않도록 설정할 사용자 계정을 두 번 Enterprise Voice.

6. 패널이 나타나면 할당된 정책 옆의 연필 아이콘 **을 클릭합니다**.

7. 할당 **된 정책** 패널의 전화 통신 **에서** 드롭다운 목록에서 **Enterprise Voice 옵션을 클릭합니다**.

8. **저장** 을 클릭합니다.

    > [!NOTE]
    > 사용자가 오디오 또는 화상 통화를 하지 않도록 제한하려면 전화 통신에서 오디오/비디오 사용 안 하도록 **설정을 클릭합니다**.

이제 사용자가 Enterprise Voice 없습니다. 

> [!NOTE]
> 2015년 8월에는 새 제어판을 비즈니스용 Skype 서버 없습니다.

### <a name="disable-a-user-account-for-enterprise-voice-using-legacy-control-panel"></a>레거시 제어판을 Enterprise Voice 사용자 계정을 사용하지 않도록 설정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.

3. 왼쪽 창에서 사용자를 **클릭합니다**.

4. **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.

5. 표에서 사용자 계정에서 사용하도록 설정할 사용자 계정을 Enterprise Voice.

6. **편집** 메뉴에서 **세부 정보 표시** 를 클릭합니다.

7. **Lync Server 사용자 편집** 페이지의 **전화 통신** 아래에서 **Enterprise Voice** 를 제외한 아무 옵션이나 클릭합니다.

    > [!NOTE]
    > 사용자가 Lync를 사용하여 오디오 또는 화상 통화를 하지 않도록 제한하려면 전화 통신에서 오디오/비디오 사용 안 **하도록 설정을 클릭합니다**.

8. **커밋** 을 클릭합니다.

이제 사용자가 Enterprise Voice 없습니다.

관련 정보: <br/>[Enterprise Voice 및 모바일](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [사용자가 Enterprise Voice 사용하도록 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [비즈니스용 Skype 서버 관리 쉘](../management-shell.md)

## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 사용자 비즈니스용 Skype 서버 제거

다음 절차에 따라 이전에 추가한 사용자 계정을 제거할 수 비즈니스용 Skype 서버.

> [!NOTE]
> 사용자를 제거하면 사용자 계정에 대해 구성한 모든 설정이 손실됩니다. 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 이전에 사용자 계정을 사용하도록 설정한 사용자 계정 사용 안 하도록 설정 또는 다시 활성화를 [비즈니스용 Skype 서버.](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

### <a name="remove-a-user-using-the-new-control-panel"></a>새 제어판을 사용하여 사용자 제거

1. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.
 
2. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정을 사용하여 로그인합니다.

3. 왼쪽 창에서 사용자를 **선택합니다**.

4. 검색 **상자** 에 표시 이름의 전체 또는 첫 번째 부분을 입력하고 찾기를 **클릭합니다**.

5. 표에서 제거할 사용자 계정을 두 번 클릭합니다.

6. 패널이 나타나면 사용자 제거 **를 클릭합니다**. 다음 패널이 나타나면 확인을 **클릭합니다**.

> [!NOTE]
> 2015년 8월에는 새 제어판을 비즈니스용 Skype 서버 없습니다.

### <a name="remove-a-user-using-the-legacy-control-panel"></a>레거시 제어판을 사용하여 사용자 제거

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.

3. 왼쪽 창에서 사용자를 **선택합니다**.

4. 사용자 검색  상자에 제거할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력한 다음 찾기를 **클릭합니다**.

5. 표에서 제거할 사용자 계정을 클릭합니다.

6. **동작** 메뉴에서 **Lync Server에서 제거** 를 선택하면 대화 상자가 나타납니다.

7. 대화 상자에서 **확인** 을 선택하여 사용자를 제거합니다.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>cmdlet이 있는 Windows PowerShell 계정 제거

이 cmdlet을 사용하여 사용자 계정을 제거할 Disable-CsUser 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 사용하여 서버에 연결하는 비즈니스용 Skype 서버 [자세한 내용은 Microsoft Lync Remote PowerShell Administration을 참조합니다](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). 프로세스는 동일한 비즈니스용 Skype 서버.

사용자 계정을 제거하려면 Disable-CsUser cmdlet을 사용합니다. 예를 들면 다음과 같습니다.

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

이 명령을 실행한 후에는 계정 및 이전 설정을 다시 사용하도록 설정할 수 없습니다. 대신 Enable-CsUser cmdlet을 사용하여 Ken Myer에 대해 새 계정을 만들어야 합니다.

자세한 내용은 [Disable-CsUser](/powershell/module/skype/disable-csuser) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="see-also"></a>참고 항목

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csuser)
