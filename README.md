# test_project

from selenium import webdriver
import pytest

browser = webdriver.Chrome()
browser.implicitly_wait(5)

link = "https://yandex.ru"
browser.get("link")

entry_field_text = None
button_search = None


class TestMainPage():

    def test_one(self):
        browser.get("link")
        assert "https://yandex.ru" == browser.get(
            "link"), "ожидаемый результат стартовая страница яндекса"

    def test_two(self):
        browser.get("link")
        entry_field_text = browser.find_element_by_id("text")

    def test_tree(self):
        browser.get("link")
        assert entry_field_text is "https://yandex.ru/", "отсутствует поле ввода"

    def test_four(self):
        browser.get("link")
        entry_field_text.send_keys("Тензор")
