## .vimrc 설정

```vim
set rtp+=~/.vim/bundle/Vundle.vim

call vundle#begin()
	Plugin 'VundleVim/Vundle.vim'
	Plugin 'morhetz/gruvbox'
call vundle#end()

" 1. 화면 설정
syntax on               " 형식별 구문 강조 표시
colorscheme gruvbox	" 테마 적용
set background=dark
set nu			" 라인 넘버 표시
set showcmd 	        " 사용자가 입력한 명령한 표시
set relativenumber      " 커서를 기준으로 라인 넘버 표시. 커서 위치에 따라 바뀜.
set cursorline 	        " 커서가 있는 라인을 강조 표시.
set ruler	        " 커서 위치 표시
set laststatus=2        " 상태바 표시
set statusline=%F\ %y%m%r\ %=Line:\ %l/%L\ [%p%%]\ Col:%c\ Buf:%n
hi statusline ctermfg=White ctermbg=4 cterm=none 
			" line 10 : 활성화된 상태바 배경색 및 폰트색 설정
hi statuslineNC ctermfg=White ctermbg=8 cterm=none
			" line 12 : 윈도우가 2개 이상인 경우 비활성화된 윈도우의 배경색 및 폰트색 설정
set mouse=a 		" 마우스로 스크롤 및 리사이즈 가능.

" 2. 들여쓰기 설정
set autoindent	        " 새로운 라인이 추가될 때, 이전 라인의 들여쓰기에 자동으로 맞춤.
set expandtab	        " Tab을 Space로 변경.
set tabstop=4	        " 탭으로 들여쓰기시 사용할 스페이스바 개수
set shiftwidth=4	" 스페이스바 n개를 하나의 탭으로 처리.
set softtabstop=4	" 스페이스바 n개를 하나의 탭으로 처리.
filetype indent on	" indent.vim 파일에 설정된 파일 형식별 들여쓰기 적용.

" 3. 입력 설정
set clipboard=unnamed	" vim에서 복사한 내용이 클립보드에 저장
set backspace=eol,start,indent  " 라인의 시작과 끝의 들여쓰기를 백스페이스로 지움.
set history=1000        " 편집한 내용 저장 개수
set paste               " 다른 곳에서 복사한 내용을 붙여넣을 때, 자동 들여쓰기가 적용되는 것을 막아 복사한 내용을 들여쓰기 없이 복사.
set pastetoggle=<F2>    " paste 옵션이 적용되면 들여쓰기가 옵션이 제대로 작동하지 않기 때문에 toggle식으로 옵션을 키고 끌 수 있음.

" 4. 검색 설정
set hlsearch		" 검색된 결과 강조 표시
set ignorecase		" 검색시 대소문자를 구분하지 않음.
set incsearch		" 검색어를 입력할 때마다 일치하는 문자열을 강조해서 표시.
set smartcase		" ignore 옵션이 켜져있더라도 검색어에 대문자가 있다면 정확히 일치하는 문자열을 찾음.

"if &term =~ "xterm"
"    "256 color --
"    let &t_Co=256
"    " restore screen after quitting
"    set t_ti=ESC7ESC[rESC[?47h t_te=ESC[?47lESC8
"    if has("terminfo")
"        let &t_Sf="\ESC[3%p1%dm"
"        let &t_Sb="\ESC[4%p1%dm"
"    else
"        let &t_Sf="\ESC[3%dm"
"        let &t_Sb="\ESC[4%dm"
"    endif
"endif
```