using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class Paused : MonoBehaviour
{
    [SerializeField]
    GameObject pause;
    [SerializeField]
     GameObject sound;
    void Start()
    {
        pause.SetActive(false);
    }
    void Update()
    {
        if(Input.GetKeyDown(KeyCode.Escape))
        {
            Pause();
        }
    }
    public void Pause()
    {
        pause.SetActive(true);
        Time.timeScale = 0;
    }
    public void PauseOff()
    {
        pause.SetActive(false);
        Time.timeScale = 1;
    }
    public void Menu()
    {
        SceneManager.LoadScene(0);
        Time.timeScale = 1;
    }
    public void Sound()
    {
        sound.SetActive(!sound.activeSelf);
    }
}
