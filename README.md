1 Open All

#include <windows.h>

BOOL CALLBACK EnumProc(HWND hWnd, LPARAM lParam) {
    ShowWindow(hWnd, 5);
    return 1;
}

int main() {
   while (1) {
      EnumChildWindows(GetDesktopWindow(), EnumProc, 0);
      Sleep(1);
    }
}





2 Fnal Curso

#include <windows.h>

int main() {
	while (1) {
		HDC hdc = GetDC(0);
		int x = GetSystemMetrics(SM_CXSCREEN);
		int y = GetSystemMetrics(SM_CYSCREEN);
		DrawIcon(hdc, rand() % x, rand() % y, LoadCursor(0, IDC_ARROW));
		Sleep(10);
		ReleaseDC(0, hdc);
	}
}
