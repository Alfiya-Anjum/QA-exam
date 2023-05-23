# QA-exam
import unittest
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from webdriver_manager.chrome import ChromeDriverManager
import time
from selenium.webdriver.common.action_chains import ActionChains

driver = webdriver.Chrome(ChromeDriverManager().install())
from tests.helpers.support_functions import *

hovers_header = '//*[@id="content"]/ul/li[25]/a'
hovers_content = 'content'
user_one = '//*[@id="content"]/div/div[1]/img'
user_two = '//*[@id="content"]/div/div[2]/img'
user_three = '//*[@id="content"]/div/div[3]/img'
link_one = '//*[@id="content"]/div/div[1]/div/a'
link_two = '//*[@id="content"]/div/div[2]/div/a'
link_three = '//*[@id="content"]/div/div[3]/div/a'


def click_tab(driver_instance):
    theelement = driver_instance.find_element_by_xpath(hovers_header)
    theelement.click()


def hovers_visible(driver_instance):
    wait_for_visibility_of_element_id(driver_instance, hovers_content)
    theelement = driver_instance.find_element_by_id(hovers_content)
    return theelement.is_displayed()


def element_click(driver_instance):
    hover_over_element(driver_instance, driver_instance.find_element_by_xpath(user_one))
    theelement = driver_instance.find_element_by_xpath(link_one)
    theelement.click()


def element_two_click(driver_instance):
    hover_over_element(driver_instance, driver_instance.find_element_by_xpath(user_two))
    theelement = driver_instance.find_element_by_xpath(link_two)
    theelement.click()


def element_three_click(driver_instance):
    hover_over_element(driver_instance, driver_instance.find_element_by_xpath(user_three))
    theelement = driver_instance.find_element_by_xpath(link_three)
    theelement.click()
